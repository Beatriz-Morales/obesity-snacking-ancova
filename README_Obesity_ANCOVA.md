# ⚖️ Obesity & Snacking Behavior — ANCOVA Analysis

**Course:** MBA Business Data Analytics — A08  
**Tools:** R · aov() · emmeans · multcomp · ggplot2  
**Dataset:** Obesity dataset — snacking frequency (CAEC), weight, age

---

## Business Problem

Does snacking frequency (never, sometimes, frequently, always) predict body weight — even after accounting for age differences across groups? This is a classic **covariate control** problem common in health analytics, HR analytics, and clinical research.

---

## What I Did

**1. Data Preparation**  
- Renamed `CAEC` → `SNACKS`; encoded as ordered factor: No / Sometimes / Frequently / Always
- Computed group-level summary statistics: n, mean weight, standard deviation by snack group

**2. ANCOVA Model**  
Fit: `WEIGHT ~ SNACKS + AGE`  
This controls for AGE as a covariate, isolating the effect of snacking behavior on weight.

**3. Adjusted Means**  
Used `emmeans` package to extract **AGE-adjusted mean weights** per snacking group — the correct post-ANCOVA comparison (not raw means).

**4. Planned Contrasts**  
Used `multcomp::glht()` with a custom contrast matrix to compare the **No-snacking group** vs. the average of all snacking groups:  
`c(1, -1/3, -1/3, -1/3)` → "Do non-snackers weigh significantly less than snackers on average?"

**5. Visualization**  
Scatter plot of `AGE vs WEIGHT` colored by `SNACKS` with separate regression lines (`geom_smooth`) per group — shows both the covariate relationship and group-level trends simultaneously.

---

## Key Findings

- **SNACKS effect:** Statistically significant (p < 2e-16) after controlling for AGE. Frequent snackers weigh more than non-snackers even when age is held constant.
- **Contrast result:** No vs. Others comparison showed p = 0.55 — the *binary* split (no snacking vs. any snacking) was NOT significant. The effect is driven by the *degree* of snacking frequency, not a simple on/off threshold.

---

## Why This Matters

ANCOVA is the correct tool when groups differ on a continuous variable that also predicts the outcome. Using raw group means without controlling for age would produce **biased estimates** — a common mistake in observational research.

---

## Files

| File | Description |
|---|---|
| `Moralesb-A08.Rmd` | Full ANCOVA with contrasts and visualization |

---

## Skills Demonstrated

`aov()` · `emmeans` · `multcomp::glht()` · Planned contrasts · Factor encoding · Group summary statistics · ANCOVA interpretation · `ggplot2` geom_smooth · Covariate control
