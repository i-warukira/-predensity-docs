# The Problem

Most prediction markets are built on AMMs — Automated Market Makers. This creates three structural flaws:

| Flaw | What it means |
|---|---|
| **Whale manipulation** | A large stake shifts the implied price before you can act |
| **Liquidity distortion** | Price reflects capital weight, not forecast quality |
| **Speculative noise** | Short-term, dopamine-driven bets crowd out genuine information |

Consider Vitalik Buterin's biotech example: you hold shares in a company that benefits from the Purple Party winning. To hedge, you buy a Yellow Party prediction token. But if a whale enters and pushes the price to $0.90, your $10 hedge no longer covers your exposure. *Your ability to hedge is entirely dependent on what the implied price is at that moment* — not on whether your forecast is correct.

This is the core failure of AMM-based prediction markets. The price is the product, not the information.

| Tool | Limitation |
|---|---|
| Perpetual futures | Signal fades beyond hours; funding rate explains little over weeks |
| AI forecasting | Works on public data only; cannot aggregate diverse private information |
| Binary AMM markets | One market per question; whale-sensitive; no continuous [price discovery](solution.md) |
| Token launchpads | Signal concentrated at listing; thin and noisy post-launch |
