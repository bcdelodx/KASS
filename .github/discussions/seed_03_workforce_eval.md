# Seed Discussion 3: Research & Policy Application

**Category:** Research & Policy Applications
**Title:** Best practices for evaluating workforce development programs?

---

## Content to Post:

I'm leading an evaluation of a state workforce development initiative and want to ensure we're using appropriate causal inference methods. Looking for community input on evaluation design choices.

## Program Context

**Intervention:**
- Subsidized training for unemployed workers
- Participants self-select into program
- Rolling enrollment over 3-year period (2020-2023)
- Multiple training tracks (healthcare, tech, skilled trades)

**Data available:**
- Administrative UI (unemployment insurance) wage records
- Program participation records with enrollment dates
- Demographic and prior employment history for participants and non-participants
- Quarterly earnings data 5 years pre-enrollment, up to 2 years post-completion

**Policy questions:**
1. What's the causal effect on earnings?
2. Do effects vary by training track or participant characteristics?
3. What's the cost-benefit ratio (meets OMB standards)?
4. Are there differential effects for disadvantaged populations?

## Evaluation Design Considerations

**Method options I'm considering:**

**Option 1: Matching + DID**
- Match participants to non-participants on observables
- Use pre/post comparison to difference out time-invariant unobservables
- Pros: Combines strengths of both approaches
- Cons: Requires good comparison group and parallel trends

**Option 2: Instrumental Variables**
- Use distance to nearest training center as instrument
- Relevance: Affects participation
- Exclusion restriction: Distance shouldn't affect earnings except through program
- Concerns: Questionable exclusion restriction (distance might correlate with labor market conditions)

**Option 3: Regression Discontinuity**
- Program has income eligibility threshold
- But threshold enforcement was inconsistent during COVID
- Fuzzy RDD possible but weak first stage

**Option 4: Heterogeneous Treatment Effects**
- Use causal forest approach from KASS notebook 11
- Estimate conditional average treatment effects
- Discover which subgroups benefit most
- Inform targeting decisions

## Specific Questions

1. **Selection bias concerns:** Participants self-select and likely differ on unobservables (motivation, job search intensity). How worried should I be that matching won't sufficiently address this?

2. **Timing issues:** Enrollment is staggered. Does this affect DID implementation? Should I use event study approach instead?

3. **Heterogeneity:** Training tracks are very different. Should I estimate effects separately by track, or pool and look for heterogeneity?

4. **Cost-benefit analysis:** What's the minimum detectable effect size I need to justify the program cost? How do I choose power analysis parameters?

5. **Federal reporting:** Needs to meet WIOA (Workforce Innovation & Opportunity Act) requirements. Are there specific methodological standards I should be aware of?

## What Would You Do?

If you were designing this evaluation:
- Which identification strategy would you prioritize?
- What robustness checks are essential?
- What are the biggest threats to validity I should address?
- Any papers or examples of similar evaluations done well?

Appreciate any insights from folks who've done workforce program evaluations or have relevant causal inference expertise.

---

## Additional Context

Budget allows for comprehensive analysis, so we can implement multiple approaches if that strengthens the evaluation. Findings will inform:
- Program continuation decision
- Potential expansion to other states
- Targeting and outreach strategy

Getting this right matters for both policy and participants.
