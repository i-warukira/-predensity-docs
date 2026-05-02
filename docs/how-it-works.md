# How a Prediction Works

A prediction has four inputs:

| Input | Description | Example |
|---|---|---|
| Asset | What you're forecasting | ETH |
| Range | Price interval $$[y_1, y_2]$$ | $3,500 – $3,700 |
| Time horizon | Resolution timestamp $$x$$ | 72 hours from now |
| Stake | USDC committed | $100 |

At time $$x$$, the oracle checks the actual price $$p$$:

$$\text{Win} = \begin{cases} \text{true} & \text{if } y_1 \leq p \leq y_2 \\ \text{false} & \text{otherwise} \end{cases}$$

If the bet wins, payout is calculated from the **Prediction Quality** score locked in at placement time.

> *The stake is locked until resolution. There are no early exits.*
