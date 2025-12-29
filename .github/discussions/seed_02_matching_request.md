# Seed Discussion 2: Feature Request

**Category:** Feature Requests & Ideas
**Title:** Request: Matching methods notebook

---

## Content to Post:

Would love to see a comprehensive notebook on matching methods added to KASS.

## The Need

Many policy evaluations can't use diff-in-diff or RDD because:
- Treatment timing is staggered and individual-specific
- No clear discontinuity or natural experiment
- But we have rich pre-treatment covariates that could support selection-on-observables identification

## Proposed Solution

A matching methods notebook covering:

**Core methods:**
- Propensity score matching (1:1, 1:k, kernel)
- Coarsened exact matching
- Entropy balancing
- Mahalanobis distance matching

**Diagnostic toolkit:**
- Balance tests (standardized differences, variance ratios)
- Common support assessment
- Sensitivity analysis (Rosenbaum bounds)
- Placebo outcome tests

**Implementation decisions:**
- How to choose matching algorithm
- Caliper selection
- Handling non-overlap
- Standard error calculation (accounting for matching)

## Use Cases

This would be valuable for:
- Program evaluation where participants self-select (job training, education programs)
- Policy analysis where treatment roll-out was non-random but recorded
- Observational studies with rich administrative data
- Situations where we can credibly argue "selection on observables"

## Alternatives Considered

Could adapt the heterogeneous treatment effects notebook (11-HTE) since it uses propensity scores, but:
- That's focused on discovering heterogeneity, not just average effects
- Doesn't cover balance diagnostics comprehensively
- Doesn't discuss matching-specific inference issues

## I Can Help By

- [x] Providing domain expertise on where matching is used in workforce policy
- [x] Testing the implementation on real use cases
- [ ] Writing the notebook (would need guidance on KASS standards)
- [x] Reviewing methodology

## Additional Context

Matching methods are workhorses of applied program evaluation, especially in:
- Labor economics (training program evaluation)
- Education (school choice, intervention programs)
- Healthcare (treatment effectiveness studies)

Having a rigorous, well-documented implementation would be hugely valuable for practitioners who need these methods but want to ensure they're applying them correctly.

---

**Thoughts from maintainers or community on priority and approach?**
