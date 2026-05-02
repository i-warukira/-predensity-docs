# Appendix: Technical Parameters

This section covers the mathematical foundations of Predensity's scoring and payout system. It is intended for developers, researchers, and technically curious readers.

---

## Lead Time Quality

Predictions are accepted for lead times between **1 and 1,000 hours**. The quality score for a given lead time is:

$$W(t) = a \cdot t^{b}$$

Where $$t$$ is the lead time in hours. Initial parameters: $$a = 17.78$$, $$b = 0.25$$

| Period | Lead Time (hours) | Quality Score |
|---|---|---|
| 1 hour | 1 | 17.8 |
| 4 hours | 4 | 25.1 |
| 1 day | 24 | 39.4 |
| 3 days | 72 | 51.8 |
| 1 week | 168 | 64.0 |
| 2 weeks | 336 | 76.1 |
| 1 month | 720 | 92.1 |

---

## Local Confidence and Boldness

Local confidence answers: given all active bets right now, what probability does the market assign to a specific price range at a specific future time?

Each bet's influence decays over time:

$$w_i = s_i \cdot e^{-r_i \cdot t_i}$$

Where $$s_i$$ is the stake, $$r_i$$ is the decay rate, and $$t_i$$ is time since placement in days.

The probability surface across all time-price combinations:

$$P(x, y) = \frac{1}{Z} \sum_{i=1}^{n} w_i \cdot K(x - x_i,\ y - y_i)$$

Where $$K()$$ is a 2D Gaussian kernel and $$Z$$ is a normalization constant.

For a fixed resolution time $$x$$, local confidence for a price range $$[y_1, y_2]$$:

$$\text{LocalConfidence}(x) = \frac{\int_{y_1}^{y_2} P(x,y)\, dy}{\int_{-\infty}^{\infty} P(x,y)\, dy}$$

Boldness is the inverse:

$$\text{Boldness} = 1 - \text{Local Confidence}$$

A prediction landing in a region the market has largely ignored scores close to 1. A prediction that follows the crowd scores close to 0.

---

## Sharpness Quality

Sharpness measures how narrow a predicted range is relative to the current token price:

$$\text{Sharpness Score} = 1 - e^{-\frac{\text{High} - \text{Low}}{\text{Current Price} \times k}}$$

Initial parameter: $$k = 0.25$$

| Range as % of Price | Sharpness Score | Interpretation |
|---|---|---|
| 5% | 0.993 | Very precise, high conviction |
| 10% | 0.950 | Sharp |
| 25% | 0.630 | Balanced |
| 50% | 0.390 | Broad |
| 100% | 0.220 | Very wide, low conviction |

---

## Prediction Quality Formula

$$\text{Prediction Quality} = S \times (\text{Lead Time Quality})^{w_L} \times (\text{Boldness Quality})^{w_B} \times (\text{Sharpness Quality})^{w_S}$$

Initial weights: $$w_L = w_B = w_S = \frac{1}{3}$$. Scaling factor $$S = 1$$ at launch, calibrated via Monte Carlo simulation.

Exponential weighting ensures a strong prediction must be balanced across all three dimensions. Exceptional sharpness cannot compensate for following the crowd. Exceptional boldness cannot compensate for a very wide range.

---

## Base Payout

$$\text{Base Payout} = \min(\text{Reserve Liquidity},\ \text{Stake} + \text{Stake} \times \text{Prediction Quality})$$

Reserve Liquidity acts as a cap — the system will never pay out more than the reserve currently holds.

---

## Reserve Bonus

When the reserve exceeds its target level, a bonus pool is made available:

$$\text{Bonus Pool}_t = \min(\text{EMA}_t,\ R_t - R_{\text{target}}) \quad \text{if } R_t > R_{\text{target}}, \text{ else } 0$$

The EMA tracks recent losing stake inflows:

$$\text{EMA}_t = \alpha \cdot L_t + (1 - \alpha) \cdot \text{EMA}_{t-1}$$

Smoothing factor: $$\alpha = 0.2$$

Each winning bet's share of the bonus pool:

$$\text{BonusShare}_i = \frac{w_i}{\sum_j w_j} \quad \text{where} \quad w_i = s_i \cdot e^{-\lambda(T - t_i)}$$

Decay rate: $$\lambda = \frac{1}{48}$$ (2-day half-life)

---

## Total Payout

$$\text{Total Payout} = \text{Base Payout} + \text{Reserve Bonus}$$
