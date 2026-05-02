# Payouts

Payouts come from each token's **liquidity reserve** — funded entirely by losing stakes. No external subsidies. No inflation.

$$\text{Total Payout} = \text{Base Payout} + \text{Reserve Bonus}$$

---

## **Base Payout**

$$\text{Base Payout} = \min\!\left(R_t,\ \text{Stake} \times (1 + \text{Prediction Quality})\right)$$

$$R_t$$ = current reserve size (acts as a solvency cap).

A 0.5% protocol fee is deducted at placement. This ensures even theoretically positive-EV bets are unprofitable if they carry no real information — *wide ranges that game the system are filtered out naturally*.

---

## **Reserve Bonus**

Activated only when the reserve exceeds its target level $$R_{\text{target}}$$:

$$\text{Bonus Pool}_t = \begin{cases} \min(\text{EMA}_t,\ R_t - R_{\text{target}}) & \text{if } R_t > R_{\text{target}} \\ 0 & \text{otherwise} \end{cases}$$

The EMA tracks recent losing stake inflows, smoothing volatility:

$$\text{EMA}_t = \alpha \cdot L_t + (1 - \alpha) \cdot \text{EMA}_{t-1}, \quad \alpha = 0.2$$

Each winning bet's share of the bonus pool, weighted by stake and recency:

$$\text{BonusShare}_i = \frac{w_i}{\sum_j w_j}, \quad w_i = s_i \cdot e^{-\lambda(T - t_i)}, \quad \lambda = \tfrac{1}{48}$$

*$$\lambda = 1/48$$ gives a 2-day half-life — recent winners capture more of the surplus.*

---

## **Reserve Management**

- Target level at launch: **$1M** per major token
- Each token has an *isolated* reserve — no cross-token exposure
- System continuously monitors reserve health and tunes $$S$$, weights, and decay rates to maintain stability
