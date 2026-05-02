# Competitive Landscape

| | **Predensity (WKP/DPM)** | AMM Binary Markets | Perpetual Futures |
|---|---|---|---|
| Model | Weighted Kernel Parimutuel + DPM | AMM liquidity pools | Order book |
| Bet format | Range $$[y_1, y_2]$$ at time $$x$$ | Yes / No tokens | Long / Short |
| Reward driver | [Sharpness × Lead time](prediction-quality.md) | Fixed odds at trade | P&L on size |
| Whale resistance | Sharpness filter caps $$a_u$$ regardless of stake | None — capital = influence | Partial |
| Liquidity | Self-funded from losing stakes | Requires external LPs | Order book depth |
| Resolution | Automatic oracle | Oracle, disputable | Mark price |
| Early exit | DPM virtual surplus (where available) | Yes — sell position | Yes — close anytime |
| Forecast output | Live density surface $$p(x)$$ | Per-market probabilities | Funding rate |
| Information value | High — precision is rewarded | Low — noise-tolerant | Medium |
