# How a Prediction Works

A prediction has four inputs:

| Input | Description | Example |
|---|---|---|
| Asset | What you're forecasting | ETH |
| Range | Price interval $$[y_1, y_2]$$ | $3,500 to $3,700 |
| Time horizon | Resolution timestamp $$x$$ | 72 hours from now |
| Stake | USDC committed | $100 |

When you place a bet, you are contributing a **kernel** to the collective market density surface. Your kernel is centered on the midpoint of your range $$x_u = (y_1 + y_2) / 2$$ and weighted by your [quality score](prediction-quality.md):

$$a_u = \text{stakeNet} \times \frac{\text{qualityBps}}{10{,}000}$$

At time $$x$$, the oracle checks the actual price $$p$$. If $$y_1 \leq p \leq y_2$$, the bet wins and [payout](payouts.md) is calculated from $$a_u$$.

The card shows a live breakdown of [sharpness, lead time](prediction-quality.md), combined quality, estimated fee, and estimated profit *before* you confirm the bet.

> *The stake is locked until resolution. [There are no early exits](no-early-exits.md), unless DPM exit liquidity is available.*
