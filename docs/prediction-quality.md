# Prediction Quality

Every bet is scored on three dimensions at placement. Scores are *locked in* — they do not change after the fact.

$$\text{Prediction Quality} = S \times Q_L^{w_L} \times Q_B^{w_B} \times Q_S^{w_S}$$

Initial weights: $$w_L = w_B = w_S = \tfrac{1}{3}$$. Scaling factor $$S = 1$$ at launch.

Exponential weighting means *no single dimension can compensate for weakness in another*. A great prediction must be sharp, bold, and early — all at once.

---

## **Sharpness** $$Q_S$$

*How narrow is the predicted range relative to the current price?*

$$Q_S = 1 - e^{-\frac{y_2 - y_1}{p_0 \cdot k}}, \quad k = 0.25$$

| Range / Price | $$Q_S$$ |
|---|---|
| 5% | 0.993 |
| 10% | 0.950 |
| 25% | 0.630 |
| 50% | 0.390 |
| 100% | 0.220 |

A 5% window on a $3,400 token = $170 range. Hitting it is hard. The system pays accordingly.

---

## **Boldness** $$Q_B$$

*How far does the prediction deviate from current market consensus?*

$$Q_B = 1 - \text{LocalConfidence}_{[y_1, y_2]}(x)$$

Where local confidence is the share of probability mass the current market assigns to $$[y_1, y_2]$$ at time $$x$$:

$$\text{LocalConfidence}(x) = \frac{\int_{y_1}^{y_2} P(x,y)\, dy}{\int_{-\infty}^{\infty} P(x,y)\, dy}$$

$$P(x,y)$$ is the live probability surface built from all active bets (see [Probability Map](probability-map.md)).

- Prediction follows the crowd → $$Q_B \approx 0$$
- Prediction goes against the crowd → $$Q_B \approx 1$$

---

## **Lead Time** $$Q_L$$

*How far in advance was the prediction placed?*

$$Q_L = a \cdot t^{b}, \quad a = 17.78,\ b = 0.25$$

Where $$t$$ is lead time in hours. Accepted range: $$t \in [1, 1000]$$.

| Lead Time | $$Q_L$$ |
|---|---|
| 1 hour | 17.8 |
| 1 day | 39.4 |
| 3 days | 51.8 |
| 1 week | 64.0 |
| 1 month | 92.1 |
