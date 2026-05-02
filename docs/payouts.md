# Payouts

Predensity uses a **Weighted Kernel Parimutuel (WKP)** payout model. All stakes in a resolution bucket go into a shared pool. Winners split that pool proportionally by kernel weight $$a_u$$.

$$\text{Payout}_i = \frac{a_{u,i}}{\sum_{j \in \text{winners}} a_{u,j}} \times \text{Bucket Total Stake}$$

Where $$a_u = \text{stakeNet} \times \text{Quality}_{bps} / 10{,}000$$

*No fixed odds. No house edge beyond the protocol fee. The pool is entirely redistributed to winners weighted by precision.*

---

## **Example**

Bucket total stake: **1,000 USDC**. Three winning bets:

| Bet | Stake | Quality | $$a_u$$ |
|---|---|---|---|
| A | 100 USDC | 2.0x | 200 |
| B | 100 USDC | 1.0x | 100 |
| C | 50 USDC | 4.0x | 200 |

Total winning weight = 500

| Bet | Payout |
|---|---|
| A | (200 / 500) x 1,000 = **400 USDC** |
| B | (100 / 500) x 1,000 = **200 USDC** |
| C | (200 / 500) x 1,000 = **400 USDC** |

*Bet C staked half of A but matched A's payout, because [quality](prediction-quality.md) doubled its kernel weight.*

---

## **Whale resistance**

A whale staking large capital on a wide range earns a 0.1x [sharpness multiplier](prediction-quality.md), limiting $$a_u$$ regardless of stake size. To move the virtual price of a sharp kernel, a whale must be equally precise. If they aren't, they are simply providing exit liquidity for the sharp stakers they are trying to displace. This is the **manipulation tax**.

---

## **No winners**

If no bet in a bucket wins, the entire bucket stake is retained by the protocol.

---

## **Fee**

A **1% fee** is deducted at placement:

$$\text{stakeNet} = \text{stake} \times 0.99$$

Quality and $$a_u$$ are calculated on $$\text{stakeNet}$$.
