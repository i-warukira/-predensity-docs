# Prediction Quality

Every bet is scored on two dimensions at placement. The score is *locked in* — it does not change after the fact.

$$\text{Quality}_{bps} = \frac{Q_S \times Q_L}{10{,}000}$$

$$\text{Weight} = \frac{\text{Stake}_{net} \times \text{Quality}_{bps}}{10{,}000}$$

Weight determines your share of the payout pool. Higher quality = larger share.

---

## **Sharpness** $$Q_S$$

*How narrow is the predicted range relative to the asset price?*

$$\text{width}_{bps} = \frac{(y_2 - y_1) \times 10{,}000}{\bar{p}}, \quad \bar{p} = \frac{y_1 + y_2}{2}$$

| Range width | $$Q_S$$ multiplier |
|---|---|
| > 40% | 0.1× |
| 20 – 40% | 0.3× |
| 10 – 20% | 0.5× |
| 5 – 10% | 1.0× |
| 2 – 5% | 1.5× |
| < 2% | **2.0×** |

*A sub-2% range on a $3,400 token = a $68 window. Hitting it earns the maximum sharpness multiplier.*

---

## **Lead Time** $$Q_L$$

*How far in advance was the prediction placed?*

Let $$\delta = t_{resolution} - t_{now}$$:

| Lead time $$\delta$$ | $$Q_L$$ multiplier |
|---|---|
| < 1 hour | 0.1× |
| 1 – 2 hours | 0.1× |
| 2 – 8 hours | 0.3× |
| 8 hours – 1 day | 0.5× |
| 1 – 2 days | 1.0× |
| 2 – 4 days | 1.5× |
| > 4 days | **2.0×** |

---

## **Combined Quality**

$$\text{Quality}_{bps} = \frac{Q_S \times Q_L}{10{,}000}$$

**Example:** Sharp range (2×) + 5-day lead time (2×) → Quality = 4× → Weight = 4 × Stake

The multipliers are applied together — *a wide range cannot be rescued by an early placement, and a last-minute bet cannot be rescued by a tight range.*
