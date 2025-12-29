# 📚 Common Causal Inference Questions – Start Here Before Posting

Before asking a new methodological question, check if it's already answered here. If you don't find your answer, absolutely ask—just reference this thread so we know you've done your homework.

## Method Selection

### Q: When should I use difference-in-differences vs. synthetic control?

A: 
- **DID** when you have multiple treated units, clear treatment timing, and can plausibly argue parallel trends
- **Synthetic Control** when you have one (or few) treated units, comparison units with different pre-treatment trends, and need to construct an explicit counterfactual

Key trade-off: DID gives you more statistical power but requires stronger assumptions. Synthetic control is more flexible but has wider confidence intervals.

See: [14-synthetic-control-policy-lab.ipynb](../../notebooks/causal-inference/14-synthetic-control-policy-lab.ipynb)

---

### Q: What's the difference between heterogeneous treatment effects and subgroup analysis?

A: Subgroup analysis splits your sample and estimates separate treatment effects—but this can mislead if groups differ on unobservables. Heterogeneous treatment effect methods (like causal forests) use machine learning to discover effect variation while properly controlling for confounding.

Critical distinction: Traditional subgroups require you to choose groupings ex-ante. HTE methods discover them from the data.

See: [11-heterogeneous-treatment-effects.ipynb](../../notebooks/causal-inference/11-heterogeneous-treatment-effects.ipynb)

---

### Q: How do I know if my regression discontinuity design is valid?

A: Run these diagnostic tests:
1. **Continuity of covariates** at threshold (should see no jump)
2. **Manipulation testing** (McCrary density test for bunching)
3. **Bandwidth sensitivity** (results shouldn't flip with reasonable bandwidth changes)
4. **Placebo cutoffs** (shouldn't see effects at fake thresholds)

If any of these fail, your identification is suspect.

See: [15-regression-discontinuity-toolkit.ipynb](../../notebooks/causal-inference/15-regression-discontinuity-toolkit.ipynb)

---

## Data & Implementation

### Q: Do I need administrative data for these methods?

A: No, but it helps. Administrative data gives you:
- Larger sample sizes → more power
- Longer time series → better pre-treatment validation
- Richer covariates → stronger controls

Survey data can work if your sample size and time coverage are adequate. The key is having good counterfactual observations, not necessarily administrative records.

---

### Q: How do I handle missing data in causal inference?

A: Carefully. Missing data mechanisms interact with causal identification:
- **Missing Completely at Random (MCAR)**: Reduces power but doesn't bias estimates
- **Missing at Random (MAR)**: Can bias if missingness correlates with treatment
- **Missing Not at Random (MNAR)**: Serious threat to validity

Solutions depend on the mechanism. Multiple imputation helps with MAR. MNAR often requires sensitivity analyses or additional assumptions.

---

### Q: What sample size do I need?

A: It depends on:
- Expected effect size (smaller effects need more observations)
- Outcome variance (noisier outcomes need more observations)
- Number of time periods (panel data gives you more effective observations)
- Clustering structure (if applicable)

Rule of thumb: You need enough power to detect the minimum policy-relevant effect size. If you can't detect an effect that would justify the intervention, your study isn't useful even if it's statistically significant.

---

## Interpretation & Reporting

### Q: How do I interpret a treatment effect estimate?

A: Always report:
1. **Magnitude**: Is the effect size policy-relevant?
2. **Precision**: How wide are the confidence intervals?
3. **Identification**: What variation identifies this effect?
4. **Limitations**: What would invalidate this estimate?

Never report just the coefficient and p-value.

---

### Q: What if I don't find a significant effect?

A: Null results are informative if:
- You had adequate power to detect policy-relevant effects
- Your identification strategy was credible
- You can rule out effects above a certain magnitude

Don't torture your data until it confesses. Sometimes policies don't work.

---

### Q: How do I explain causal inference to non-technical audiences?

A: Focus on the comparison, not the math:
- "We compared similar [units] that did and didn't get the policy"
- "We checked whether trends were similar before the policy"
- "We ruled out alternative explanations like [X, Y, Z]"

Use visualizations. Show the counterfactual explicitly. Avoid jargon.

---

## Contributing to This FAQ

Found a question you keep seeing? Reply to this thread with:
- The question (as you've seen it asked)
- A clear, concise answer
- Links to relevant notebooks or papers

We'll update the main post regularly.
