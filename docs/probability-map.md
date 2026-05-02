# The Prediction Chart

Each market displays a live chart built from all active bets. This is the visual representation of the **market density surface** $$p(x)$$ — the collective kernel aggregation.

## **How the density is built**

Each bet contributes a kernel centered on its midpoint price $$x_u$$, weighted by $$a_u$$ (its [on-chain quality weight](prediction-quality.md)):

$$p(x) \propto \sum_u \left[ a_u \times R(x_u, x) \right]$$

Where $$R(x_u, x) = \gamma^{|x_u - x| / \Delta}$$ is the kernel decay function. On the frontend this is implemented via `d3.contourDensity` with a Gaussian kernel and adaptive bandwidth $$\Delta$$. The `weight(a_u)` call sums each bet's kernel contribution across the entire price-time plane.

Band probabilities — the confidence contour thresholds (25% / 50% / 75%) — slice the continuous density into interpretable regions.

---

## **What the chart shows**

| Element | Meaning |
|---|---|
| Scatter dots | Individual bets at their target resolution time and midpoint price — sized by $$a_u$$ |
| Median line | Running weighted median of all bets — updates step-by-step as new bets arrive |
| P25–P75 band | Middle 50% of stake-weighted opinion — tighter = stronger consensus |
| Current price | Live oracle price overlaid in green |

*Time filters (1d / 1w / 1m / all) narrow the view to bets resolving within a specific window.*

The chart is read-only — it does not feed into the quality score. It exists to show you where the crowd's kernel mass is concentrated before you decide where to place yours.
