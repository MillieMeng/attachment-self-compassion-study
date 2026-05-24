# Attachment Styles, Self-Compassion & Emotional Distress

**A quantitative archival analysis · PSYCH-UA 300 · NYU, Spring 2026**

---

## The Question

Do the ways we attach to others predict how much we suffer emotionally — and does self-compassion play a role? This project uses archival data from 473 Korean college students (Joeng et al., 2017) to examine three interrelated questions about attachment, depression, anxiety, and self-compassion.

---

## Key Findings at a Glance

| Research Question | Method | Result |
|---|---|---|
| Do anxious & avoidant attachment predict depression? | Multiple linear regression | ✅ Both significant (*p* < .001); R² = .306 |
| Do gender & university group affect anxiety? | Two-way ANOVA | ❌ No significant effects |
| Do males & females differ in self-compassion? | Independent samples *t*-test | ❌ No significant difference |

> **Headline result:** Attachment styles explained ~30% of the variance in depression. Both anxious attachment (*B* = 0.18) and avoidant attachment (*B* = 0.21) were significant positive predictors — even after controlling for each other.

---

## Dataset

- **Source:** Joeng, J. R., et al. (2017). *Data in Brief*, 14, 7–11.
- **N = 473** Korean college students across two universities
- **Variables used:** Anxious attachment (ECR-R), avoidant attachment (ECR-R), self-compassion (SCS), depression (CES-D), trait anxiety (STAI-T), gender, university group

---

## Methods & Analysis

### Analysis 1 — Multiple Linear Regression

**Question:** Do anxious and avoidant attachment predict depression?

**Approach:** Fit `depression ~ anxious_attachment + avoidant_attachment` in R. Checked normality (Shapiro-Wilk), homoscedasticity (NCV test), and linearity (residual plots).

**Results:**
- Model: *F*(2, 470) = 103.7, *p* < .001, *R*² = .306
- Anxious attachment: *B* = 0.18, *SE* = 0.03, *t*(470) = 6.26, *p* < .001
- Avoidant attachment: *B* = 0.21, *SE* = 0.02, *t*(470) = 9.86, *p* < .001
- Mild violations of normality and homoscedasticity detected; results interpreted with caution

**Interpretation:** Both insecure attachment styles independently predicted higher depression. Avoidant attachment showed a slightly stronger effect, possibly reflecting the cumulative cost of suppressing emotional needs over time.

---

### Analysis 2 — Two-Way ANOVA

**Question:** Do gender and university group affect trait anxiety — and do they interact?

**Approach:** `anxiety ~ gender * group` in R. Checked normality (Shapiro-Wilk on residuals) and homogeneity of variance (Levene's test).

**Results:**
- Gender: *F*(1, 469) = 0.34, *p* = .561 — not significant
- University group: *F*(1, 469) = 0.01, *p* = .911 — not significant
- Interaction: *F*(1, 469) = 0.87, *p* = .351 — not significant
- Levene's test: *p* = .731 (assumption met)

**Interpretation:** Anxiety levels were remarkably stable across demographic groups. The homogeneous sample (Korean college students) and possible cultural factors — such as similar socialization around emotional expression — may have suppressed variability.

---

### Analysis 3 — Independent Samples *t*-test

**Question:** Do males and females report different levels of self-compassion?

**Approach:** `t.test(self_compassion ~ gender, var.equal = TRUE)` in R. Checked homogeneity of variance with Levene's test first.

**Results:**
- Males: *M* = 3.14, *SD* = 0.57 (*n* = 288)
- Females: *M* = 3.14, *SD* = 0.63 (*n* = 185)
- *t*(471) = −0.055, *p* = .956, 95% CI [−0.11, 0.11]
- Levene's test: *p* = .060 (assumption met)

**Interpretation:** Self-compassion scores were virtually identical across genders. This null finding may reflect the cultural context: Confucian values around collectivism and self-restraint may shape self-compassion similarly for men and women in this sample.

---

## Repository Structure

```
attachment-self-compassion-study/
│
├── README.md                          ← You are here
│
├── analysis/
│   └── MillieMeng_FinalProject.Rmd    ← Full annotated R Markdown script
│
└── report/
    └── MillieMeng_FinalProject_WriteUp.pdf  ← APA-formatted write-up
```

---

## Tools & Skills

`R` · `tidyverse` · `ggplot2` · `car` · `readxl`

Statistical methods: multiple linear regression · two-way ANOVA · independent samples *t*-test · assumption testing (Shapiro-Wilk, Levene's, NCV)

---

## Citation

Joeng, J. R., Turner, S. L., Kim, E. Y., Choi, S. A., Lee, Y. J., & Kim, J. K. (2017). Data on relationships among self-compassion, mindfulness, compassion satisfaction, burnout, and secondary traumatic stress. *Data in Brief*, 14, 7–11. https://doi.org/10.1016/j.dib.2017.07.042

---

*Millie Meng · Psychology B.A. · New York University · Class of 2027*
