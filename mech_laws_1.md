%md
# Phase 2 Summary: The Three Governing Hazard Laws

---

## Law 1 — Attempt Timing (Weibull Hazard)

$$T_{ij} \sim \text{Weibull}(k,\; \theta_i \cdot \lambda)$$

| Parameter | Role |
|-----------|------|
| $k$ | Shape — shared universally; $k < 1$ means hazard is highest right after last attempt (bursts) |
| $\theta_i$ | Student velocity — the single latent scalar per student |
| $\lambda$ | Shared timescale |

**Variance collapse test**: Dividing gaps by $\theta_i$ reduces the population CV, validating that $\theta_i$ absorbs between-student heterogeneity. Remaining spread is within-student noise.

---

## Law 2 — Pass-Given-Attempt (Logistic)

$$P(\text{pass}\;|\;\text{attempt}) = \sigma\bigl(\alpha_i + \gamma_j + \beta \cdot \text{order} + \delta \cdot \text{OBJA}\bigr)$$

| Parameter | Role |
|-----------|------|
| $\alpha_i$ | Student ability — same latent scalar family as $\theta_i$ |
| $\gamma_j$ | Course difficulty — fixed effect per course node |
| $\beta$ | Attempt-order learning effect (fail → learn → retry) |
| $\delta$ | Assessment type adjustment (OBJA vs PRFA) |

**Key signal**: AUC lifts from baseline (attempt-order only) when adding $\alpha_i + \gamma_j$ — validates that individual and course-level state, not just attempt count, governs passing.

---

## Law 3 — Dormancy / Drop (Logistic Gap Model)

$$P(\text{drop this month}) = \sigma\bigl(\beta_0 + \beta_1 \cdot \ln(1 + T_{\max})\bigr)$$

| Parameter | Role |
|-----------|------|
| $T_{\max}$ | Maximum inter-attempt gap in the month |
| $\beta_1 > 0$ | Longer gap → higher drop risk |

**Structural check**: Dropper Weibull shape $k \approx$ persister shape $k$. Same law — droppers differ only in effective $\theta_i \to 0$, not in a different process. This validates the unification of drop and dormancy.

---
