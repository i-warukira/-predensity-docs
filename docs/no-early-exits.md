# No Early Exits

In a pure WKP model, liquidity is locked in the kernel until the market resolves. Predensity layers a **Dynamic Parimutuel (DPM)** cost function, from Microsoft Research (2004), over the WKP pool to introduce exit liquidity without the predatory mechanics of an AMM.

---

## **How DPM exit works**

Each kernel submitted is treated as a purchase of *sharp shares*. As the total pool grows, the cost to mint new shares in the same range increases. This means:

- If you placed a sharp prediction *before the crowd*, the market-implied value of your shares rises as later bettors pile in
- You can sell your shares back to the pool at the current instantaneous price
- The system pays you from the *virtual surplus* created by later, less-informed bettors
- *You exit with a profit (your certainty equivalent) before the market resolves*

**The house never takes a loss:** every stake paid out to an early exiter was paid in by a later participant.

---

## **Default behavior**

For most markets, stakes remain locked until resolution. DPM exit is available where the pool has sufficient depth. Locked positions ensure the [prediction chart](probability-map.md) reflects genuine committed views, not positions that can be placed and quietly withdrawn.
