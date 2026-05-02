# The Solution

Predensity replaces the AMM with a **Weighted Kernel Parimutuel (WKP)** model.

Instead of buying a price, you contribute a *kernel*: a forecast centered on a price range $$[y_1, y_2]$$ at a future time $$x$$. Your influence on the collective market view is proportional to the *quality* of your forecast, not the size of your stake alone.

At time $$x$$, an oracle fetches the actual price $$p$$:

$$\text{Win} = \begin{cases} \text{true} & \text{if } y_1 \leq p \leq y_2 \\ \text{false} & \text{otherwise} \end{cases}$$

**The key difference from AMMs:** your ability to profit is not dependent on what the implied price is right now. It depends on how precise your forecast is relative to the final result. A whale cannot move your payout by flooding the pool with capital, because payout is weighted by [sharpness and lead time](prediction-quality.md), not raw stake size.

No market creation. No liquidity bootstrapping. No manual resolution.

Layered on top of WKP is a **[Dynamic Parimutuel (DPM)](https://www.microsoft.com/en-us/research/video/a-dynamic-pari-mutuel-market-for-hedging-wagering-and-information-aggregation/)** cost function, drawn from Microsoft Research (2004), which introduces exit liquidity into the kernel space. See [Payouts](payouts.md) for how this works.
