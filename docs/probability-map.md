# The Prediction Chart

Each market displays a live chart built from all active bets on that token.

The chart plots two things simultaneously:

**1. Scatter dots** — one per bet, positioned at its *target resolution time* (x-axis) and *midpoint price* (y-axis). Dot size reflects [stake weight](prediction-quality.md).

**2. Community prediction line** — a running weighted median of all bets placed so far, with a shaded **P25–P75 confidence band** around it. This updates step-by-step as each new bet is added.

A horizontal **current price line** is overlaid in green for reference.

---

**What it tells you:**

| Element | Meaning |
|---|---|
| Median line | Where the crowd's stake-weighted consensus sits right now |
| P25–P75 band | The middle 50% of stake-weighted opinion — tighter = more consensus |
| Scatter dots | Individual predictions — clustered dots = crowded price zone |
| Current price | Live oracle price for comparison |

*Time filters (1d / 1w / 1m / all) let you narrow the view to bets resolving within a specific window.*

The chart is read-only — it does not feed into the [quality score](prediction-quality.md). It exists to help you see where the crowd is before you decide where to predict.
