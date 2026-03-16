# ⚖️ Obesity & Snacking ANCOVA

**Course:** MBA Business Data Analytics  
**Tools:** R · ggplot2 · dplyr · ANCOVA · emmeans  
**Dataset:** Obesity and behavioral dataset with age, snacking frequency, and weight-related variables

---

## Business Problem

Does snacking frequency significantly influence weight outcomes after controlling for age?  
This project applies ANCOVA to test whether behavioral differences in snacking are associated with obesity-related outcomes while adjusting for a continuous covariate.

---

## What I Did

**1. Data Preparation**  
- Loaded and explored the obesity-related dataset in R
- Reviewed variable distributions, factor levels, and summary statistics
- Identified snacking frequency as the categorical predictor and age as the covariate
- Prepared the response variable for ANCOVA modeling

**2. ANCOVA Modeling**  
- Built an ANCOVA model to evaluate mean differences in weight-related outcomes across snacking groups
- Controlled for age to isolate the effect of snacking behavior
- Examined model assumptions and significance results
- Used adjusted means to compare group-level outcomes

**3. Post-Model Interpretation**  
- Applied estimated marginal means (`emmeans`) for adjusted group comparisons
- Interpreted how snacking frequency related to the response after accounting for age
- Translated statistical results into practical behavioral insight

---

## Key Insight

The analysis tested whether differences in snacking behavior remained associated with weight outcomes even after adjusting for age, demonstrating how ANCOVA can separate group effects from covariate influence.

---

## Business Value

- Demonstrated how ANCOVA can be used for behavior-based analysis
- Showed how to control for a confounding variable in group comparisons
- Highlighted the importance of adjusted means in interpreting real-world differences
- Reinforced the value of statistical modeling for health-related analytics

---

## Files

| File | Description |
|---|---|
| `moralesb-ancova.Rmd` | Full ANCOVA analysis and adjusted mean comparison workflow |

---

## Skills Demonstrated

ANCOVA · Covariate adjustment · Estimated marginal means · Group comparison · Statistical interpretation · Behavioral analytics · R Markdown
