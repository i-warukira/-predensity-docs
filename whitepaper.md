# Predensity Whitepaper

---

## Abstract

Most people who trade crypto have a view. They watch the charts, follow the news, read the threads — and they form an opinion about where a token is going. But there has never been a clean way to express that opinion, get rewarded for being right, and contribute something useful to the broader market in the process.

Predensity changes that.

Predensity is a decentralized prediction market, live on Hedera, where anyone can forecast the future price of a crypto token — or the outcome of a sports match, a political event, a financial metric — and earn real rewards for being bold, early, and accurate. Not just correct. The system specifically rewards people who go against the grain, commit early, and pin down a precise range. That combination of traits is what makes a prediction genuinely valuable, and Predensity is built to recognize and reward it.

The platform starts with crypto price forecasting and expands from there. Every prediction placed feeds into a shared, live probability map — a crowd-sourced picture of where the market thinks things are heading. That map is a public good. Anyone can read it. The more people participate, the more useful it becomes.

---

## The Problem with How Markets Work Today

Crypto is one of the most speculative asset classes in the world, and yet the tools available to ordinary traders are surprisingly limited when it comes to expressing a genuine view.

Perpetual futures let you go long or short, but they're built for short-term positioning — minutes to hours. Their predictive signal fades fast. Over a week, the funding rate tells you almost nothing about where a token will actually trade.

AI forecasting tools have gotten better at trend analysis and pattern recognition, but they're working with the same public data everyone else has. They can sharpen your thinking, but they can't replace the kind of distributed, diverse intelligence that comes from thousands of people with different information and different perspectives all putting money behind their views.

Traditional prediction markets like Polymarket are genuinely useful for discrete events — elections, regulatory decisions, one-off outcomes. But they're built around yes/no questions, and every question needs its own market, its own liquidity pool, its own resolution process. That model fragments attention and capital. It also can't give you a continuous view of price expectations over time — it was never designed to.

Token launchpads create a burst of speculative energy around new listings, but that energy dissipates quickly. The post-launch price signal is thin, noisy, and easily manipulated.

The gap in all of this is the same: there is no continuous, crowd-sourced, incentive-aligned mechanism for expressing and aggregating price expectations across time. That is what Predensity is built to fill.

---

## What Predensity Does Differently

The core idea behind Predensity is simple: instead of asking "will this happen or not," we ask "where do you think this will be, and when?"

A trader on Predensity doesn't pick yes or no. They pick a price range and a time horizon. "I think ETH will be between $3,500 and $3,700 three days from now." They back that view with USDC. At the specified time, a price oracle checks the actual price. If it falls within the predicted range, the bet wins.

No market needs to be created in advance. No liquidity provider needs to seed a pool. No moderator needs to adjudicate the outcome. The system handles all of it automatically.

What makes Predensity genuinely different from anything else is what happens next — how it decides what a winning bet is worth.

Being right is the minimum requirement. What the system actually rewards is the *quality* of being right. A prediction that was narrow, went against the crowd, and was placed days in advance is worth far more than one that was wide, followed the consensus, and was placed an hour before resolution. Both might win. But they are not equally valuable, and Predensity treats them accordingly.

This is the insight at the heart of the platform: the most useful predictions are the ones that are hardest to make. Rewarding difficulty — not just correctness — is what turns a betting market into a genuine information system.

---

## How a Prediction Works

When you place a prediction on Predensity, you specify four things:

**What you're predicting.** A crypto token, a sports match outcome, a political result, a financial metric. The platform currently supports crypto price markets and is expanding to sports, politics, finance, and technology.

**Your range.** For crypto, this is a price interval — say, $3,500 to $3,700. For other categories, it's the equivalent measurable range for that outcome type.

**Your time horizon.** When should the prediction resolve? You can predict anywhere from one hour to over a month out. The further out you go, the harder it is — and the more you can earn.

**Your stake.** How much USDC you're putting behind the prediction.

At resolution time, the oracle fetches the actual value. If it falls within your range, you win. Your payout is your stake back, plus a reward calculated from your Prediction Quality score.

---

## What Makes a Prediction High Quality

Every prediction on Predensity is scored on three dimensions the moment it's placed. These scores are locked in — they don't change after the fact.

**Sharpness** is about precision. A range of $3,500–$3,600 on a $3,400 token is a 3% window. A range of $2,000–$5,000 is a 90% window. The narrower your range, the harder it is to hit, and the more you earn if you do. Sharpness rewards conviction.

**Boldness** is about independence. At any given moment, the platform has a live probability map built from all active bets. If most of the money is clustered around $3,400–$3,500 and you're calling $3,700–$3,800, your prediction is bold — it diverges from the consensus. Bold predictions that land earn significantly more than ones that follow the crowd. Boldness rewards original thinking.

**Lead time** is about timing. Predicting where ETH will be in three days is harder than predicting where it will be in three hours. The earlier you commit, the more you earn if you're right. Lead time rewards foresight.

These three scores are combined into a single Prediction Quality multiplier using exponential weighting. The reason for exponential rather than additive weighting is deliberate: a great prediction has to be strong across all three dimensions. You can't make up for a very wide range by placing the bet early. You can't make up for following the crowd by being extremely precise. The system is designed to reward predictions that are genuinely hard to make — sharp, bold, and early all at once.

---

## The Probability Map

Every active bet on Predensity feeds into a live, continuously updated probability distribution. Think of it as a heat map stretched across two axes: price on one side, time on the other. The darker the region, the more stake-weighted confidence the market has placed there.

This map serves two purposes.

First, it's the basis for calculating boldness. When you place a prediction, the system looks at where your range sits on the current map. If you're predicting into a low-confidence region — somewhere the crowd hasn't gone — your boldness score is high. If you're predicting exactly where everyone else is, your boldness score is low.

Second, it's a public good. The map is free to read. Traders can use it to understand where market sentiment is concentrated. Researchers can use it to study how crowd forecasts evolve over time. Bots can consume it as a real-time signal. The more people participate in Predensity, the more accurate and useful the map becomes — which in turn attracts more participants. It's a self-reinforcing loop.

The map applies decay weighting to older bets, so it stays responsive to new information. A prediction placed a week ago carries less weight than one placed an hour ago. The map reflects the current state of market thinking, not a historical average.

---

## No Early Exits

Once you place a prediction on Predensity, your stake is locked until the market resolves. There is no way to withdraw early, close your position, or transfer it to someone else.

This is a deliberate design choice, not a limitation.

Locked positions mean every prediction is a genuine commitment. When capital is at stake and can't be retrieved, people think harder before placing a bet. The signal quality goes up. The probability map becomes more trustworthy because every data point in it represents a real, committed view — not a position someone placed speculatively and might exit at any moment.

It also keeps the system honest. If early exits were allowed, sophisticated actors could place bets to move the probability map in a direction that benefits their other positions, then exit before resolution. Locking positions removes that attack vector entirely.

The no-exit rule also shapes how the platform is used. Predensity is not a trading platform where you manage positions in real time. It's a forecasting platform where you express a view, commit to it, and find out if you were right. That's a different kind of engagement — and for many people, a more satisfying one.

---

## How Payouts Work

When a prediction wins, the payout comes from the token's liquidity reserve — a pool funded entirely by the stakes of losing bets. There are no external subsidies, no protocol token inflation, no liquidity providers taking a cut. The system is self-sustaining by design.

The payout has two components.

The **base payout** is your stake back plus a reward calculated from your Prediction Quality score. The higher your quality score — the sharper, bolder, and earlier your prediction — the larger the multiplier. The base payout is capped by the current size of the reserve to ensure the system never pays out more than it holds.

The **reserve bonus** kicks in when the reserve has grown beyond its target level. When there's surplus in the reserve — because more bets have been lost than the system needs to cover future payouts — a portion of that surplus is distributed to winning bets as a bonus. The bonus is proportional to stake size and weighted toward more recent winning bets. It scales with market activity: busy periods generate more losing stakes, which grow the reserve, which makes the bonus pool larger.

The reserve target for major tokens at launch is set at $1 million. The system monitors reserve health continuously and adjusts its parameters to keep payouts sustainable as the platform grows.

---

## Markets

Predensity launches with crypto price prediction markets. This is the most natural starting point — crypto prices are continuous, oracle-verifiable, and the subject of intense speculation by a large global audience. Supported assets at launch include BTC, ETH, SOL, and other major tokens.

The platform is designed to expand. The same prediction and payout mechanics work for any outcome that can be expressed as a measurable range at a future timestamp:

**Sports** — final scores, player statistics, match outcomes across football, basketball, tennis, cricket, and more. The platform already supports a rich taxonomy of sports and leagues.

**Politics** — vote share percentages, approval ratings, electoral college outcomes, seat counts. Political events are some of the most-discussed prediction market categories globally.

**Finance** — stock prices, commodity prices, economic indicators like inflation rates and GDP figures. Traditional finance meets decentralized forecasting.

**Technology** — company valuations, product launch metrics, IPO prices, user growth figures. Tech outcomes that are hard to bet on anywhere else.

Each category has its own smart contract deployed on Hedera mainnet. The resolution mechanism is oracle-based and automatic — no human adjudication, no disputes, no delays.

---

## The Platform

Predensity is live on **Hedera mainnet**. Hedera was chosen for its fast finality, low and predictable transaction fees, and enterprise-grade reliability — properties that matter when real money is on the line and predictions need to resolve on time.

Staking is denominated in **USDC**, giving traders a stable unit of account that doesn't introduce currency risk on top of prediction risk.

Getting started requires no crypto experience. Users sign in with their email address through Magic Link, which automatically creates a non-custodial wallet. There are no seed phrases to write down, no browser extensions to install, no gas tokens to acquire before you can start. Your wallet is yours — Predensity never holds your private keys and cannot access your funds.

For users in East Africa, the platform supports **M-Pesa deposits**, bridging Kenyan shillings directly to USDC. This makes Predensity accessible to a large population of mobile-first users who have historically been excluded from crypto-native platforms.

All smart contracts are publicly verifiable on HashScan. The platform charges a 0.5% fee on all bets at placement, routed to the protocol treasury to support ongoing development.

---

## Why This Matters

There is a version of prediction markets that is just gambling dressed up in blockchain clothes. Predensity is not that.

The goal is to build a system where the act of making a prediction — and being rewarded for making a good one — produces something genuinely useful for everyone. The probability map that emerges from Predensity's activity is a real-time, crowd-sourced forecast of future prices and outcomes. It aggregates information from thousands of people with different knowledge, different models, and different risk tolerances. No single analyst, no AI system, and no trading algorithm can replicate that.

When incentives are aligned correctly — when the system rewards quality over quantity, boldness over conformity, and foresight over reaction — the crowd becomes smarter than any individual. That is the principle Predensity is built on. And the output of that crowd intelligence is a public good that benefits everyone who participates, and many who don't.

---

## Competitive Landscape

| | Predensity | Polymarket | Perpetual Futures |
|---|---|---|---|
| Market structure | Continuous price × time | Discrete binary events | Continuous price only |
| How you bet | Pick a price range and time horizon | Buy yes/no outcome tokens | Go long or short |
| Liquidity | Self-funded from losing stakes | AMM-backed, needs LPs | Exchange order book |
| Resolution | Automatic via price oracle | Oracle-based, can be disputed | Mark price, continuous |
| What earns more | Sharp, bold, early predictions | Fixed odds at trade time | P&L on position size |
| Can you exit early | No — locked until resolution | Yes — sell your position | Yes — close anytime |
| Forecast output | Live public probability map | Per-market outcome probabilities | Funding rate signal |
| Chain | Hedera | Polygon | Various |

---

## Appendix: Technical Parameters

The following section covers the mathematical foundations of Predensity's scoring and payout system. It is intended for developers, researchers, and technically curious readers.

### Lead Time Quality

Predictions are accepted for lead times between 1 and 1,000 hours. The quality score for a given lead time is calculated as:

```
W(t) = a · t^b
```

Where `t` is the lead time in hours. Initial parameters: `a = 17.78`, `b = 0.25`.

| Period | Lead Time (hours) | Quality Score |
|---|---|---|
| 1 hour | 1 | 17.8 |
| 4 hours | 4 | 25.1 |
| 1 day | 24 | 39.4 |
| 3 days | 72 | 51.8 |
| 1 week | 168 | 64.0 |
| 2 weeks | 336 | 76.1 |
| 1 month | 720 | 92.1 |

### Local Confidence and Boldness

Local confidence answers the question: given all the active bets on the platform right now, what probability does the market assign to a specific price range at a specific future time?

It is computed using a 2D kernel density estimate (KDE) of all outstanding bets, weighted by stake size and decayed by time since placement. Each bet's influence diminishes as it ages:

```
w_i = s_i · e^(−r_i · t_i)
```

Where `s_i` is the stake, `r_i` is the decay rate, and `t_i` is time since placement in days.

The probability surface across all time-price combinations is:

```
P(x, y) = (1/Z) · Σ w_i · K(x − x_i, y − y_i)
```

Where `K()` is a 2D Gaussian kernel and `Z` is a normalization constant.

For a fixed resolution time `x`, the local confidence for a price range `[y₁, y₂]` is:

```
LocalConfidence(x) = ∫(y₁ to y₂) P(x,y) dy  /  ∫(−∞ to ∞) P(x,y) dy
```

Boldness is the inverse of local confidence:

```
Boldness = 1 − Local Confidence
```

A prediction that lands in a region the market has largely ignored scores close to 1. A prediction that follows the crowd scores close to 0.

### Sharpness Quality

Sharpness measures how narrow a predicted range is relative to the current token price. The raw sharpness ratio is:

```
Range Sharpness = (High − Low) / Current Price
```

This is mapped to a normalized score between 0 and 1 using an exponential function:

```
Sharpness Score = 1 − e^(−Range Sharpness / k)
```

Initial parameter: `k = 0.25`

| Range as % of Price | Sharpness Score | What it means |
|---|---|---|
| 5% | 0.993 | Very precise, high conviction |
| 10% | 0.950 | Sharp |
| 25% | 0.630 | Balanced |
| 50% | 0.390 | Broad |
| 100% | 0.220 | Very wide, low conviction |

### Prediction Quality Formula

The three quality dimensions are combined using exponential weighting:

```
Prediction Quality = Scaling Factor × (Lead Time Quality)^wL × (Boldness Quality)^wB × (Sharpness Quality)^wS
```

Initial weights: `wL = wB = wS = 1/3`. Scaling Factor: `1` at launch, calibrated via Monte Carlo simulation.

Exponential weighting is used rather than additive weighting because a strong prediction must be balanced across all three dimensions. Exceptional sharpness cannot compensate for following the crowd. Exceptional boldness cannot compensate for a very wide range.

### Base Payout

```
Base Payout = min(Reserve Liquidity, Stake + Stake × Prediction Quality)
```

Reserve Liquidity acts as a cap — the system will never pay out more than the reserve currently holds.

### Reserve Bonus

When the reserve exceeds its target level, a bonus pool is made available to winning bets:

```
Bonus Pool_t = min(EMA_t, R_t − R_target)    if R_t > R_target, else 0
```

The EMA tracks recent losing stake inflows:

```
EMA_t = α · L_t + (1 − α) · EMA_(t−1)
```

Smoothing factor: `α = 0.2`

Each winning bet's share of the bonus pool is proportional to its stake, weighted toward more recent bets:

```
BonusShare_i = w_i / Σ w_j     where w_i = s_i · e^(−λ(T − t_i))
```

Decay rate: `λ = 1/48` (2-day half-life)

Total payout for a winning bet:

```
Total Payout = Base Payout + Reserve Bonus
```

---

*Predensity is live at [predensity.com](https://www.predensity.com)*
