# Prediction Quality

Every bet is scored on two dimensions at placement. The score is *locked in* and does not change after the fact.

$$\text{Quality}_{bps} = \frac{Q_S \times Q_L}{10{,}000}$$

$$a_u = \text{stakeNet} \times \frac{\text{Quality}_{bps}}{10{,}000}$$

$$a_u$$ is the bet's **kernel weight**: its influence on the [collective market density](probability-map.md) and its share of the [payout pool](payouts.md). Higher quality = larger $$a_u$$.

No single dimension can compensate for weakness in another. A great prediction must be sharp and early, both at once.

---

## **Sharpness** $$Q_S$$

*How narrow is the predicted range relative to the asset price?*

The sharpness function is a discrete step approximation of the kernel decay:

$$R(x_u, x) = \gamma^{|x_u - x| / \Delta}$$

Where $$\gamma$$ is the decay factor and $$\Delta$$ is the scale parameter (what counts as one unit of error). On-chain, this is implemented as a step function on $$\text{width}_{bps}$$:

$$\text{width}_{bps} = \frac{(y_2 - y_1) \times 10{,}000}{\bar{p}}, \quad \bar{p} = \frac{y_1 + y_2}{2}$$

| Range width | $$Q_S$$ multiplier |
|---|---|
| > 40% | 0.1x |
| 20 to 40% | 0.3x |
| 10 to 20% | 0.5x |
| 5 to 10% | 1.0x |
| 2 to 5% | 1.5x |
| < 2% | **2.0x** |

*A sub-2% range on a $3,400 token = a $68 window. The sharpness filter also acts as whale protection: a large stake on a wide range earns only a 0.1x multiplier, limiting its influence on the kernel.*

---

## **Lead Time** $$Q_L$$

*How far in advance was the prediction placed?*

Let $$\delta = t_{resolution} - t_{now}$$:

| Lead time $$\delta$$ | $$Q_L$$ multiplier |
|---|---|
| < 2 hours | 0.1x |
| 2 to 8 hours | 0.3x |
| 8 hours to 1 day | 0.5x |
| 1 to 2 days | 1.0x |
| 2 to 4 days | 1.5x |
| > 4 days | **2.0x** |

---

## **Combined Quality and Weighted Dilution**

$$\text{Quality}_{bps} = \frac{Q_S \times Q_L}{10{,}000}$$

**Example:** A $100 stake with a sharp range (2x) and 5-day lead time (2x) gives Quality = 4x and $$a_u = 400$$

A whale staking $10,000 on a wide range (0.1x) with 1-hour lead time (0.1x) gives Quality = 0.01x and $$a_u = 100$$

*The $100 sharp stake commands 4x more kernel influence than the $10,000 whale stake. This is weighted dilution: precision beats capital.*
