# 🎯 Show & Tell: Share Your KASS-Powered Analyses

Built something using KASS methods? We want to see it.

Sharing your work helps:
- Other researchers see what's possible
- The community learn from real applications
- The maintainers understand how KASS is being used
- Your organization demonstrate methodological rigor

## What to Share

**Ideal posts include:**
- The policy question you were answering
- Which KASS notebook(s) you used as foundation
- Key methodological decisions you made
- What you learned (both analytically and about the method)
- (Optional) Link to publication, report, or public repo

**You can share work at any stage:**
- Published papers or reports
- Work-in-progress analyses
- Replications of existing studies using KASS methods
- Failed analyses where you learned something valuable

## Confidentiality Note

Don't share:
- Proprietary or sensitive data
- Internal organizational information
- Personally identifiable information
- Anything that would violate data use agreements

You can absolutely describe your analysis in general terms without revealing sensitive details.

## Example Post Format

Here's what a good Show & Tell post looks like:

---

**Policy Question:** Did Opportunity Zone designation affect housing prices in our metro area?

**Method:** Synthetic control (adapted from [14-synthetic-control-policy-lab.ipynb](../../notebooks/causal-inference/14-synthetic-control-policy-lab.ipynb))

**Key Decisions:** 
- Used Census tract-level housing price index as outcome
- Constructed donor pool from tracts with similar pre-designation characteristics across comparable metros
- Validated with placebo tests on non-designated tracts
- Extended analysis window to 5 years post-designation

**Results:** Found 8-12% price increase in designated zones, with heterogeneity by urban vs. rural setting. Effect emerged gradually over 2-3 years rather than immediately.

**What I Learned:** 
- Initial specification showed implausibly large magnitudes—turned out I had a data scaling issue where prices were in thousands but I treated them as dollars
- Placebo tests caught it before I reported bad estimates
- Parallel pre-trends assumption was violated in initial donor pool selection; had to tighten matching criteria

**Impact:** Internal report for city council. Informed affordable housing policy discussions and led to targeted displacement mitigation strategies.

**Code/Paper:** [Link if publicly available]

---

## Ready to Share?

Post your work below using the example format as a guide. We're excited to see what you've built!

**First to post gets featured in our next newsletter.** 👀
