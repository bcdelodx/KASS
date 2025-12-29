# 🗺️ KASS Roadmap & How to Contribute

This thread outlines what we're working on and how you can help.

## Current Status (Q1 2026)

### What's Live

- ✅ **Heterogeneous Treatment Effects** – Causal Forests, Double ML for discovering effect variation
- ✅ **Synthetic Control Methods** – Abadie-Diamond-Hainmueller methodology with inference
- ✅ **Regression Discontinuity Design** – Sharp and fuzzy RDD with diagnostic toolkit
- ✅ **Labor Market Intelligence** – Multi-source data integration for workforce analysis
- ✅ **Opportunity Zone Evaluation** – Comprehensive impact assessment framework
- ✅ **Workforce Development ROI** – Cost-benefit analysis meeting federal standards

### What's Coming (Q1-Q2 2026)

- 🔨 **Difference-in-Differences** – Canonical two-way fixed effects + event study designs
- 🔨 **Instrumental Variables** – 2SLS, LIML, weak instrument diagnostics
- 🔨 **Event Studies** – Staggered treatment timing with modern estimators
- 🔨 **Bayesian Synthetic Control** – Uncertainty quantification via posterior inference
- 🔨 **Spatial Econometrics** – Regional spillovers and geographic discontinuities

### What's Planned (Q3-Q4 2026)

- 📋 **Synthetic Difference-in-Differences** – Combines strengths of both methods
- 📋 **Machine Learning for Policy Targeting** – Predict who benefits most from interventions
- 📋 **Climate Adaptation CBA** – Cost-benefit frameworks for climate resilience investments
- 📋 **Small-Area Estimation** – Bayesian methods for data-scarce geographies
- 📋 **Interactive Policy Dashboards** – Scenario analysis and counterfactual visualization

---

## How to Contribute

### High-Value Contributions We Need

#### 1. New Methodological Notebooks

**Priority areas:**
- **Matching methods** (propensity score, coarsened exact matching, entropy balancing)
- **Bunching estimators** for tax/transfer policy analysis
- **Duration analysis** for program entry/exit dynamics
- **Geographic RDD** for border discontinuities
- **Triple differences** for differential treatment timing

**Requirements:**
- Must meet methodological standards (see [CONTRIBUTING.md](../../CONTRIBUTING.md))
- Include proper identification strategy discussion
- Provide comprehensive robustness checks and diagnostics
- Use publicly accessible data (or clear synthetic data generation)

#### 2. Applied Policy Notebooks

Show how to apply existing methods to new domains:
- Criminal justice interventions and recidivism
- Education policy evaluation (school choice, curriculum changes)
- Healthcare access programs and utilization
- Environmental regulations and compliance
- Housing and community development initiatives

These help users see how to adapt general methods to their specific context.

#### 3. Documentation Improvements

- Clearer explanations of methodology for non-experts
- Better guidance on method selection decision trees
- More interpretation examples with policy-relevant context
- Common pitfalls and how to avoid them
- Troubleshooting guides for data issues

#### 4. Code Quality Improvements

- More efficient implementations (vectorization, parallelization)
- Better error handling and input validation
- Improved visualization (clearer diagnostic plots, publication-ready figures)
- Enhanced reproducibility (better random seed management, environment specs)

### Medium-Value Contributions

- Bug fixes (always appreciated, any size)
- Additional robustness checks for existing notebooks
- Extended examples with different data sources
- Translation/localization of documentation
- Tutorial videos or blog posts explaining methods

---

## How to Propose Contributions

**Process:**

1. **Check existing issues/discussions** to avoid duplication
2. **Open a discussion** in the Feature Requests category with:
   - What you want to add
   - Why it's valuable to the community
   - Your proposed approach
   - Timeline if you plan to build it yourself
3. **Wait for maintainer feedback** before starting major work (saves everyone time)
4. **Submit PR** following [CONTRIBUTING.md](../../CONTRIBUTING.md) guidelines

**What Happens Next:**

- Maintainers review proposal within 1 week
- If aligned with roadmap: we'll assign it and provide guidance
- If not prioritized: we'll explain why and suggest alternatives
- If we decline: clear rationale provided (usually scope or quality bar concerns)

---

## What We're NOT Looking For

Be honest about limitations:

- ❌ Notebooks that don't meet methodological standards (we'll help you get there, but won't merge weak identification)
- ❌ Methods that are purely descriptive when causal inference is feasible
- ❌ Analyses using proprietary/inaccessible data that others can't reproduce
- ❌ Duplicate implementations of existing methods without clear improvement
- ❌ "My specific problem" notebooks that don't generalize

---

## Prioritization Criteria

We prioritize contributions based on:

1. **Methodological gaps** – Does this fill a real need not currently met?
2. **Generalizability** – Will this help multiple policy domains, or just one narrow use case?
3. **Quality** – Does it meet publication-quality standards?
4. **Documentation** – Is it well-explained and usable by others?
5. **Data accessibility** – Can anyone run this, or does it require special access?
6. **Maintenance burden** – Can we realistically support this long-term?

---

## Recognition & Credit

**We celebrate contributors:**
- Listed in README acknowledgments
- Featured in monthly community highlights
- Co-authorship credit on method papers (for substantial contributions)
- Early access to KRL platform features (for major contributors)
- Direct line to maintainers for future collaboration

---

## Questions About Contributing?

Reply to this thread with:
- Whether your proposed contribution fits the roadmap
- Technical requirements or standards questions
- Coordination with other contributors
- Timeline and review process concerns
- Anything else about contributing

We want to make it as easy as possible to contribute high-quality work.

---

**Want to shape the roadmap? Tell us what you need. ⬇️**
