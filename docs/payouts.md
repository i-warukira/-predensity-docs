# Payouts

Predensity uses a **parimutuel** model. All stakes in a resolution bucket go into a shared pool. Winners split that pool proportionally by weight.

$$\text{Payout}_i = \frac{w_i}{\sum_{j \in \text{winners}} w_j} \times \text{Bucket Total Stake}$$

Where $$w_i = \text{Stake}_{net,i} \times \text{Quality}_{bps,i}\ /\ 10{,}000$$

*No fixed odds. No house edge beyond the protocol fee. The pool is entirely redistributed to winners.*

---

## **Example**

Bucket total stake: **1,000 USDC**. Three winning bets:

| Bet | Stake | Quality | Weight |
|---|---|---|---|
| A | 100 USDC | 2.0× | 200 |
| B | 100 USDC | 1.0× | 100 |
| C | 50 USDC | 4.0× | 200 |

Total winning weight = 500

| Bet | Payout |
|---|---|
| A | (200 / 500) × 1,000 = **400 USDC** |
| B | (100 / 500) × 1,000 = **200 USDC** |
| C | (200 / 500) × 1,000 = **400 USDC** |

Bet C staked half of A but matched A's payout — *because quality doubled its effective weight.*

---

## **No Winners**

If no bet in a bucket wins, the entire bucket stake is retained by the protocol.

---

## **Fee**

A **1% fee** is deducted from the stake at placement:

$$\text{Stake}_{net} = \text{Stake} \times 0.99$$

Quality and weight are calculated on $$\text{Stake}_{net}$$.
