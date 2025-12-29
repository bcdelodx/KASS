# Contributing to KASS

Thank you for your interest in contributing to KASS (Knowledge & Analytics for Social Science). We welcome contributions that advance rigorous policy analysis and causal inference methods.

## Table of Contents

- [Getting Started](#getting-started)
- [Contribution Standards](#contribution-standards)
- [Notebook Requirements](#notebook-requirements)
- [Code Style & Documentation](#code-style--documentation)
- [Submission Process](#submission-process)
- [Review Process](#review-process)
- [Community Guidelines](#community-guidelines)
- [Getting Help](#getting-help)

---

## Getting Started

### Development Environment Setup

1. **Fork and clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/KASS.git
   cd KASS
   ```

2. **Set up Python environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt  # If available
   ```

3. **Install core dependencies**
   ```bash
   pip install jupyter pandas numpy scipy statsmodels econml causalml matplotlib seaborn black
   ```

4. **Set up data access** (if needed)
   - Census API key: https://api.census.gov/data/key_signup.html
   - BLS API key: https://data.bls.gov/registrationEngine/
   - Configure keys in your environment or `.env` file

### Before You Start

- Browse existing notebooks to understand our standards
- Check [open issues](../../issues) for known needs
- Review [Discussions](../../discussions) for ongoing conversations
- Consider opening an issue to discuss your idea before investing significant time

---

## Contribution Standards

All contributions must meet these quality thresholds:

### Methodological Rigor

**Clear Identification Strategy**
- Explicit statement of what variation identifies the causal effect
- Enumeration of required assumptions
- Tests that validate those assumptions

**Proper Inference**
- Appropriate standard error corrections (clustered, robust, etc.)
- Honest uncertainty quantification
- Discussion of statistical power when relevant

**Robustness Checks**
- Alternative specifications
- Placebo tests where applicable
- Sensitivity analyses for key assumptions
- Frank discussion of what the evidence does and doesn't support

### Reproducibility

**Complete Data Pipelines**
- Clear data source documentation
- Replicable data acquisition code
- Transparent cleaning and processing steps
- No unexplained "black box" transformations

**Environment Specification**
- Document all package dependencies
- Specify version requirements where critical
- Include any system-level requirements

**Deterministic Results**
- Set random seeds for stochastic methods
- Document any sources of non-reproducibility
- Provide clear instructions for replication

### Transparency

**Honest Limitations**
- Every method has boundaries - state them explicitly
- Acknowledge threats to identification
- Discuss external validity concerns
- Note any deviations from best practices and why

**Clear Documentation**
- Explain methodology, not just implementation
- Provide intuition for key concepts
- Include references to foundational papers
- Document all non-obvious design choices

---

## Notebook Requirements

### Structure

Each analytical notebook should include:

1. **Title & Overview** (first cell)
   - Clear statement of the policy question
   - Summary of the analytical approach
   - Key findings (1-3 bullets)

2. **Motivation** (markdown section)
   - Why this question matters
   - What makes causal inference necessary here
   - Policy relevance

3. **Data** (section with code)
   - Source documentation
   - Acquisition code
   - Cleaning and processing
   - Summary statistics
   - Data quality discussion

4. **Methodology** (markdown section)
   - Detailed explanation of the identification strategy
   - Why this approach is appropriate
   - Required assumptions
   - Potential threats to validity

5. **Implementation** (code sections)
   - Well-commented analysis code
   - Step-by-step progression
   - Intermediate validation checks
   - Clear variable naming

6. **Results** (mixed code/markdown)
   - Main estimates with proper inference
   - Robustness checks
   - Specification tests
   - Professional visualizations
   - Clear interpretation

7. **Limitations & Interpretation** (markdown section)
   - Honest assessment of what the analysis does/doesn't show
   - Threats to identification
   - Generalizability concerns
   - Policy implications

8. **References** (final section)
   - Citation of key methodological papers
   - Data source documentation
   - Related work

### Quality Markers

**Would this pass peer review at a top journal?**
- Identification strategy clearly articulated
- Assumptions explicitly stated and tested
- Robustness checks comprehensive
- Limitations honestly discussed

**Could a federal agency rely on this for policy decisions?**
- Meets OMB Circular A-4 standards (where applicable)
- Transparent methodology
- Reproducible results
- Professional presentation

**Can another researcher replicate and extend this?**
- Complete data pipeline
- Well-documented code
- Clear explanation of methods
- Modular, adaptable structure

---

## Code Style & Documentation

### Python Code

**Formatting**
- Follow PEP 8 style guidelines
- Use `black` for automatic formatting: `black notebook.ipynb`
- Maximum line length: 88 characters (black default)

**Naming Conventions**
- Variables: `snake_case` (e.g., `treatment_effect`, `control_group`)
- Functions: `snake_case` (e.g., `estimate_ate()`, `run_placebo_test()`)
- Classes: `PascalCase` (if needed)
- Constants: `UPPER_SNAKE_CASE` (e.g., `CENSUS_API_KEY`)

**Code Organization**
- Group related operations into functions
- Avoid deeply nested code blocks
- Use meaningful variable names (no `x1`, `temp`, `df2` unless absolutely clear)
- Include inline comments for non-obvious logic
- Add docstrings for any function >5 lines

**Example of good code style:**
```python
def estimate_treatment_effect(data, treatment_var, outcome_var, covariates):
    """
    Estimate average treatment effect using doubly robust estimation.

    Args:
        data: DataFrame with individual-level observations
        treatment_var: Name of binary treatment indicator
        outcome_var: Name of outcome variable
        covariates: List of covariate names for adjustment

    Returns:
        dict with keys 'ate', 'se', 'ci_lower', 'ci_upper'
    """
    # Propensity score model
    ps_model = LogisticRegression()
    ps_model.fit(data[covariates], data[treatment_var])
    propensity_scores = ps_model.predict_proba(data[covariates])[:, 1]

    # Outcome regression for each treatment arm
    outcome_model_treated = LinearRegression()
    # ... implementation continues
```

### Markdown Documentation

**Section Headers**
- Use clear, descriptive headers
- Follow logical hierarchy (##, ###, ####)
- Include table of contents for long notebooks

**Explanatory Text**
- Write for a technical but not necessarily specialist audience
- Explain *why*, not just *what*
- Use mathematical notation sparingly and define all symbols
- Include intuitive explanations before technical details

**Visualizations**
- Every figure needs a clear title and axis labels
- Include interpretive text immediately after each visualization
- Use colorblind-friendly palettes
- Export high-resolution versions for publication use

---

## Submission Process

### Step 1: Prepare Your Contribution

1. **Create a feature branch**
   ```bash
   git checkout -b feature/your-contribution-name
   ```

2. **Develop your notebook/improvement**
   - Follow all standards outlined above
   - Test thoroughly
   - Run all cells fresh to ensure reproducibility

3. **Format your code**
   ```bash
   black your_notebook.ipynb
   ```

4. **Clear all outputs** (for clean diffs)
   ```bash
   jupyter nbconvert --ClearOutputPreprocessor.enabled=True --inplace your_notebook.ipynb
   ```

### Step 2: Document Your Changes

Create a clear commit message:
```bash
git add .
git commit -m "Add [feature/improvement]: Brief description

- Detailed point about what changed
- Why this change improves the repository
- Any relevant context

Addresses #[issue number] if applicable"
```

### Step 3: Open a Pull Request

1. **Push your branch**
   ```bash
   git push origin feature/your-contribution-name
   ```

2. **Open PR on GitHub**
   - Provide clear title summarizing the contribution
   - In the description, explain:
     - What problem this solves or what it adds
     - Your methodological approach
     - How you tested it
     - Any dependencies or requirements
   - Link to any related issues

3. **PR Template** (use this structure):
   ```markdown
   ## Summary
   Brief description of what this PR adds or fixes

   ## Motivation
   Why is this contribution valuable?

   ## Methodology
   For new notebooks: Brief overview of identification strategy
   For improvements: What was changed and why

   ## Testing
   How did you validate this works correctly?

   ## Checklist
   - [ ] Code follows style guidelines
   - [ ] Notebook runs end-to-end without errors
   - [ ] Methodology is clearly documented
   - [ ] Limitations are honestly discussed
   - [ ] All outputs cleared before committing
   - [ ] References are complete and properly formatted
   ```

---

## Review Process

### What to Expect

**Initial Review (1-2 weeks)**
- Maintainers will assess whether the contribution aligns with repository goals
- May request clarifications or additional context
- Not all contributions will be accepted, even if technically sound

**Technical Review (2-4 weeks)**
- Detailed methodology review
- Code quality assessment
- Reproducibility testing
- May require revisions

**Revision Cycle**
- We'll work with you to meet quality standards
- Expect iterative feedback
- Focus on methodological rigor first, code polish second

### Review Criteria

**For New Notebooks:**
- Does the identification strategy meet causal inference standards?
- Are assumptions clearly stated and tested?
- Would this pass peer review at a policy-relevant journal?
- Is the code reproducible and well-documented?
- Are limitations honestly discussed?

**For Improvements to Existing Notebooks:**
- Does this enhance methodological rigor?
- Improve clarity or usability?
- Fix errors or address limitations?
- Maintain consistency with repository standards?

**For Documentation:**
- Is the explanation clearer than what exists?
- Does it help users understand when/how to apply methods?
- Is it accurate and well-sourced?

---

## Community Guidelines

### Code of Conduct Principles

We're building a community of practice around rigorous policy analysis. We expect:

**Professional Discourse**
- Critique ideas and methods, not people
- Assume good faith
- Focus on improving analytical quality
- Respectful disagreement is encouraged; personal attacks are not

**Intellectual Honesty**
- Acknowledge uncertainty and limitations
- Give credit to prior work
- Correct errors transparently
- Don't oversell results

**Inclusivity**
- Welcome researchers at all career stages
- Explain technical concepts clearly
- Share knowledge generously
- Recognize that rigorous methods serve the public good

**Constructive Feedback**
- Be specific about what needs improvement
- Explain *why* something doesn't meet standards
- Suggest paths forward
- Recognize good work

### Unacceptable Behavior

- Harassment or discriminatory language
- Intentionally misleading methodological claims
- Plagiarism or uncredited use of others' work
- Bad faith participation or trolling

Violations should be reported to [info@krlabs.dev](mailto:info@krlabs.dev).

---

## Getting Help

### Questions About Contributing

**Before opening an issue or discussion:**
- Check existing [Issues](../../issues) and [Discussions](../../discussions)
- Review this guide thoroughly
- Look at merged PRs for examples

**Where to ask:**

**Methodological questions:** [Discussions](../../discussions)
- "Is this identification strategy credible for X?"
- "How do I choose between method A and B?"
- "What robustness checks are needed here?"

**Technical implementation:** [Issues](../../issues)
- "How do I set up data access for X?"
- "This code throws an error when..."
- "Can we add support for X package?"

**Contribution ideas:** [Discussions](../../discussions) first, then issue
- "Would a notebook on X topic be valuable?"
- "I want to improve Y - thoughts on approach?"

**Direct contact:** [info@krlabs.dev](mailto:info@krlabs.dev)
- For sensitive matters
- Partnership/collaboration proposals
- Questions about the KRL platform

---

## Additional Resources

### Learning Causal Inference
- Angrist & Pischke (2009): *Mostly Harmless Econometrics*
- Cunningham (2021): *Causal Inference: The Mixtape* (free online)
- Huntington-Klein (2022): *The Effect* (free online)

### Federal Evaluation Standards
- [OMB Circular A-4](https://www.whitehouse.gov/omb/information-for-agencies/circulars/): Regulatory Impact Analysis
- [Green Book](https://www.whitehouse.gov/omb/information-for-agencies/green-book/): Benefit-Cost Analysis
- [What Works Clearinghouse Standards](https://ies.ed.gov/ncee/wwc/Handbooks)

### Python Causal Inference Libraries
- [EconML](https://github.com/microsoft/EconML): Microsoft's econometric ML library
- [CausalML](https://github.com/uber/causalml): Uber's causal inference library
- [DoWhy](https://github.com/microsoft/dowhy): Causal inference with graphical models

---

## Recognition

Contributors whose work is merged will be:
- Credited in commit history
- Acknowledged in repository documentation
- Listed as contributors on the GitHub repository
- Cited in any publications that use their contributions

Significant contributions may lead to co-authorship opportunities on related publications or collaborations with the KRL team.

---

**Thank you for helping build better policy analysis infrastructure.**

Questions? [Open a Discussion](../../discussions) or email [info@krlabs.dev](mailto:info@krlabs.dev).
