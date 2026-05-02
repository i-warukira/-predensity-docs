# The Probability Map

Every active bet contributes to a live 2D probability surface $$P(x, y)$$ — price $$y$$ on one axis, time $$x$$ on the other.

$$P(x,y) = \frac{1}{Z} \sum_{i=1}^{n} w_i \cdot K(x - x_i,\ y - y_i)$$

Where $$K()$$ is a 2D Gaussian kernel, $$Z$$ is a normalization constant, and each bet's weight decays over time:

$$w_i = s_i \cdot e^{-r_i \cdot t_i}$$

$$s_i$$ = stake, $$r_i$$ = decay rate, $$t_i$$ = days since placement.

*Older bets lose influence. The map reflects current market thinking, not a historical average.*

---

**The map serves two roles:**

1. **Boldness input** — a bet landing in a low-density region of $$P(x,y)$$ scores high on $$Q_B$$
2. **Public signal** — free to read; useful for traders, researchers, and bots tracking sentiment
