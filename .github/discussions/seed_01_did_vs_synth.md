# Seed Discussion 1: Methodological Question

**Category:** Methodological Questions
**Title:** DID vs. Synthetic Control: When to use which?

---

## Content to Post:

I'm evaluating a state-level education policy change and trying to decide between difference-in-differences and synthetic control methods. Both seem potentially applicable, but I'm not sure which is more appropriate.

**My setup:**
- **Treatment:** One state adopted new teacher compensation policy in 2018
- **Outcome:** Student test scores (panel data 2010-2023)
- **Data:** All 50 states, annual observations
- **Concern:** Treated state had different pre-treatment trend from national average

**My understanding:**
- DID requires parallel trends assumption - but visual inspection shows my treated state trending differently
- Synthetic control can handle different pre-trends by constructing weighted counterfactual
- But synthetic control gives me just one treated unit, so wider confidence intervals?

**Questions:**
1. Does the different pre-trend automatically disqualify DID?
2. Is synthetic control always preferable when you have just one treated unit?
3. Can I run both and compare results, or is that p-hacking?

Would appreciate guidance on how to think through this choice systematically.

---

## Self-Answer (post after 2-4 hours):

This is a great question that highlights the key trade-offs between these methods. Let me break down the decision criteria:

### When Different Pre-Trends Matter

The parallel trends assumption in DID requires that treated and control units would have followed the same trend **absent treatment**. If your treated state was already on a different trajectory, standard DID is indeed problematic.

However, you have options:
1. **Interactive fixed effects DID** – allows for unit-specific trends
2. **Matching on pre-treatment trends** – select comparison states with similar trajectories
3. **Synthetic control** – explicitly constructs counterfactual matching pre-treatment path

### One Treated Unit ≠ Automatic Synthetic Control

Synthetic control is designed for this case, but consider:

**Advantages:**
- Transparent about which comparison units drive counterfactual
- Doesn't require parallel trends assumption
- Visually intuitive (you see the constructed counterfactual)

**Disadvantages:**
- Wider confidence intervals (as you noted)
- Sensitive to donor pool specification
- May not find good synthetic match if treated unit is unusual

### The "Run Both" Question

Running both methods is actually good practice, **IF**:
- You pre-specify this as a robustness check
- You don't cherry-pick which result to report
- You explain why estimates differ (if they do)

Methodologically sound approach:
1. Start with your preferred method based on data structure
2. Report that result as primary estimate
3. Show alternative method as robustness check
4. If results differ substantially, investigate why

### For Your Case Specifically

Given that you have:
- One treated state
- Clear pre-treatment trend difference
- All 50 states as potential donors

**I'd recommend synthetic control as primary method:**

1. Construct synthetic control using pre-2018 data
2. Validate with placebo tests on never-treated states
3. Check sensitivity to donor pool restrictions
4. Report synthetic DID as robustness check (combines both approaches)

**Implementation:**
- Start with [14-synthetic-control-policy-lab.ipynb](../notebooks/causal-inference/14-synthetic-control-policy-lab.ipynb)
- Pay special attention to donor pool selection
- Run the diagnostic tests for synthetic match quality

**Red flags to watch for:**
- Poor pre-treatment fit (RMSPE > certain threshold)
- Weights concentrated on single donor state
- Placebo tests showing lots of false positives

Does this help clarify the decision process?

---

**Additional resources:**
- Abadie, Diamond & Hainmueller (2010) - Synthetic Control Methods for Comparative Case Studies
- Arkhangelsky et al. (2021) - Synthetic Difference-in-Differences
