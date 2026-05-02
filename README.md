# Abstract

Traditional prediction markets treat predictions as *implied prices* — making them vulnerable to whale manipulation, liquidity distortion, and speculative noise. Predensity is built on a fundamentally different model: the **Weighted Kernel Parimutuel (WKP)** system, layered with a **Dynamic Parimutuel (DPM)** cost function.

Instead of buying a price, you contribute a *forecast kernel* to a collective market density surface. Your reward is determined not by what the market price is right now, but by how precise your forecast is relative to the final outcome.

[Quality](docs/prediction-quality.md) is scored on two dimensions: **sharpness** (how narrow the range) and **lead time** (how early the prediction). These combine into a kernel weight $$a_u$$ that determines each winner's share of the [payout pool](docs/payouts.md).

---

## **Why WKP/DPM**

| Property | What it means |
|---|---|
| **Expressive** | Predict any range, any time — not just yes/no |
| **Fair** | Precision beats capital — a sharp $100 stake outweighs a lazy $10,000 stake |
| **Manipulation-resistant** | The sharpness filter caps whale influence regardless of stake size |
| **Information-rich** | Rewards boldness and precision, producing a genuine [density signal](docs/probability-map.md) |
| **Exit liquidity** | DPM cost function lets early, correct forecasters exit before resolution via virtual surplus |
| **AI-ready** | Agents can trade continuously and specialize — precision is the edge, not execution speed |

The most profitable action is also the most socially valuable one: *providing accurate, early, and precise data*.

The system starts with crypto price forecasting and expands to [sports, politics, finance, and technology](docs/markets.md). The mechanics are the same across all categories: *predict a range, commit a stake, get rewarded for quality*.
