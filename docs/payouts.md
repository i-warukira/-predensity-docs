# How Payouts Work

When a prediction wins, the payout comes from the token's liquidity reserve — a pool funded entirely by the stakes of losing bets. There are no external subsidies, no protocol token inflation, no liquidity providers taking a cut. The system is self-sustaining by design.

The payout has two components.

---

## Base Payout

Your stake back, plus a reward calculated from your Prediction Quality score. The higher your quality score — the sharper, bolder, and earlier your prediction — the larger the multiplier.

$$\text{Base Payout} = \min(\text{Reserve Liquidity},\ \text{Stake} + \text{Stake} \times \text{Prediction Quality})$$

The base payout is capped by the current size of the reserve to ensure the system never pays out more than it holds.

---

## Reserve Bonus

The reserve bonus kicks in when the reserve has grown beyond its target level. When there's surplus in the reserve — because more bets have been lost than the system needs to cover future payouts — a portion of that surplus is distributed to winning bets as a bonus.

$$\text{Total Payout} = \text{Base Payout} + \text{Reserve Bonus}$$

The bonus is proportional to stake size and weighted toward more recent winning bets. It scales with market activity: busy periods generate more losing stakes, which grow the reserve, which makes the bonus pool larger.

---

## Reserve Health

The reserve target for major tokens at launch is set at **$1 million**. The system monitors reserve health continuously and adjusts its parameters to keep payouts sustainable as the platform grows.

Each token maintains its own isolated reserve. There is no cross-token exposure — a large payout on ETH markets does not affect the BTC reserve.
