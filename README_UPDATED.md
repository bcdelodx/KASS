# KASS: Khipu Applied Statistical Science
## Production-Grade Policy Analysis with Real Data

**Status:** 🚧 In Transition (Template → Production)
**Audit Grade:** B (83/100) → Target: A (95+/100)
**Last Updated:** 2026-01-13

---

## 📊 Repository Status

### Current State

This repository is undergoing a **critical upgrade** from methodological templates to production-ready policy analysis. Based on an institutional audit (2026-01-13), we are systematically replacing simulated data with real data from authoritative sources.

| Directory | Status | Grade | Description |
|-----------|--------|-------|-------------|
| `production/` | 🚧 In Development | N/A | Real data notebooks (peer-review ready) |
| `templates/` | ✅ Complete | B (83/100) | Methodology demonstrations (simulated data) |
| `development/` | 🚧 Active | N/A | Works in progress |

---

## ⚠️ CRITICAL DATA DISCLOSURE

### Templates Directory (Current Notebooks)

**Status:** METHODOLOGICAL DEMONSTRATIONS ONLY

All notebooks in `templates/` use **simulated data** with the following characteristics:

- ❌ **Treatment effects are pre-programmed** (not empirical findings)
- ❌ **Outcome variables are calibrated simulations** (not observed data)
- ✅ **Econometric methods are correctly implemented**
- ✅ **Real FRED/BLS macro data at state/national level**
- ❌ **Metro/individual-level variation is synthetic**

### ⛔ DO NOT USE TEMPLATES FOR:
- Policy white papers citing effect sizes
- Congressional testimony or legislative briefings
- Academic peer-reviewed publications (as empirical studies)
- Executive decision-making without data upgrade
- Grant proposals using simulated treatment effects

### ✅ APPROVED USES FOR TEMPLATES:
- Methodological training and education
- Software testing and validation
- Template development for future analyses
- Preliminary exploratory analysis with explicit disclaimers

---

## 🎯 Production Roadmap

### Phase 1: NB07 Labor Market Intelligence (Months 1-3)
**Target:** A- (92/100)

- Replace simulated metro employment with BLS QCEW real data
- Integrate MSA-level unemployment from BLS LAUS
- Add LEHD job flows for employment dynamics
- **Expected Completion:** Month 3

### Phase 2: NB20 Opportunity Zone Evaluation (Months 4-6)
**Target:** A (95/100)

- Obtain official OZ designations from Treasury CDFI Fund
- Use Zillow Home Value Index for property outcomes
- Integrate ACS tract-level demographics
- **Expected Completion:** Month 6

### Phase 3: NB22 Workforce Development ROI (Months 7-12)
**Target:** A (95/100)

- Negotiate state PIRL (Participant Individual Record Layout) access
- Obtain administrative workforce program data
- Link to UI wage records for earnings outcomes
- **Expected Completion:** Month 12

---

## 📁 Repository Structure

```
KASS/
├── production/                # Real data notebooks (peer-review ready)
│   ├── 07-labor-market-intelligence.ipynb  [Coming Month 3]
│   ├── 20-opportunity-zone-evaluation.ipynb [Coming Month 6]
│   └── 22-workforce-development-roi.ipynb   [Coming Month 12]
│
├── templates/                 # Methodology demonstrations (simulated data)
│   └── notebooks/
│       ├── causal-inference/
│       │   ├── 11-heterogeneous-treatment-effects.ipynb
│       │   ├── 14-synthetic-control-policy-lab.ipynb
│       │   └── 15-regression-discontinuity-toolkit.ipynb
│       └── applied-econometrics/
│           ├── 07-labor-market-intelligence.ipynb
│           ├── 20-opportunity-zone-evaluation.ipynb
│           └── 22-workforce-development-roi.ipynb
│
├── development/               # Works in progress
│
├── data_connectors/           # KRL data connector integration
│   ├── __init__.py
│   └── kass_data_manager.py  # Unified data fetching interface
│
├── data/
│   └── cache/                 # Cached API responses
│
├── docs/
│   ├── PEER_REVIEW_CHECKLIST.md
│   └── DATA_QUALITY_STANDARDS.md
│
├── REAL_DATA_REMEDIATION_PLAN.md  # Detailed upgrade plan
└── README.md                       # This file
```

---

## 🚀 Quick Start

### For Learning Causal Inference Methods

```bash
# Use template notebooks
cd templates/notebooks/causal-inference/
jupyter notebook 15-regression-discontinuity-toolkit.ipynb
```

**Note:** These demonstrate **methods**, not real policy findings.

### For Production Policy Analysis

```bash
# Wait for production notebooks (or build your own using templates)
cd production/
# Coming soon: Real data notebooks
```

---

## 🔧 Installation

### Basic Setup (Templates Only)

```bash
# Clone repository
git clone https://github.com/KhipuResearch/KASS.git
cd KASS

# Create environment
conda create -n kass python=3.11
conda activate kass

# Install dependencies
pip install -r requirements.txt
```

### Production Setup (Real Data)

```bash
# Additional dependency for real data fetching
pip install krl-data-connectors

# Configure API credentials
export FRED_API_KEY="your_fred_key"
export BLS_API_KEY="your_bls_key"
export CENSUS_API_KEY="your_census_key"

# Test data connectors
python -c "from data_connectors import KASSDataManager; dm = KASSDataManager()"
```

---

## 📖 Notebook Guide

### Template Notebooks (Simulated Data)

#### Causal Inference
- **NB11: Heterogeneous Treatment Effects** - Machine learning for subgroup analysis
- **NB14: Synthetic Control Policy Lab** - Counterfactual policy evaluation
- **NB15: Regression Discontinuity Toolkit** - Threshold-based causal inference

#### Applied Econometrics
- **NB07: Labor Market Intelligence** - Regional employment analysis
- **NB20: Opportunity Zone Evaluation** - Place-based policy assessment
- **NB22: Workforce Development ROI** - Program cost-benefit analysis

### Production Notebooks (Real Data)
**Coming Soon** - Will mirror template structure with authentic data.

---

## 📊 Data Provenance

### Templates: Hybrid Real + Simulated

| Notebook | Macro Data | Treatment | Outcomes | Grade |
|----------|------------|-----------|----------|-------|
| NB07 | ✅ Real FRED | ❌ N/A | ❌ Simulated | B+ |
| NB20 | ✅ Real FRED | ❌ Simulated | ❌ Simulated | B+ |
| NB22 | ✅ Real FRED | ❌ Simulated | ❌ Simulated | B |
| NB15 | ✅ Real FRED | ❌ Simulated | ❌ Simulated | C+ |
| NB14 | ✅ Real FRED | ⚠️ Unclear | ⚠️ Unclear | B- |
| NB11 | ✅ Real FRED | ❌ Simulated | ❌ Simulated | B |

### Production: 100% Real Data

| Notebook | Macro Data | Treatment | Outcomes | Grade |
|----------|------------|-----------|----------|-------|
| NB07 | ✅ Real | ✅ N/A | ✅ Real QCEW | A- (target) |
| NB20 | ✅ Real | ✅ Real Treasury | ✅ Real Zillow/ACS | A (target) |
| NB22 | ✅ Real | ✅ Real PIRL | ✅ Real UI wages | A (target) |

---

## 🔬 Quality Assurance

### Institutional Standards

This repository adheres to:
- ✅ Federal Statistical Agency Standards (Census, BLS)
- ✅ Academic Peer-Review Requirements (Top Econ Journals)
- ✅ Transparency Best Practices (Data provenance badges)

### Peer Review Process

All production notebooks undergo:
1. **Methodological review** by senior statistician
2. **Data provenance verification** by data governance officer
3. **Reproducibility testing** (automated)
4. **External validity assessment**
5. **Grade certification** (minimum A- for production)

See [PEER_REVIEW_CHECKLIST.md](docs/PEER_REVIEW_CHECKLIST.md) for details.

---

## 🎓 Educational Use

### For Students

Template notebooks are **excellent learning resources** for:
- Causal inference methods (DiD, RDD, Synthetic Control)
- Machine learning for heterogeneous effects
- Policy evaluation frameworks
- Cost-benefit analysis

**Always cite as "Methodological demonstration with simulated data."**

### For Instructors

Templates can be used to:
- Teach econometric methods
- Demonstrate software workflows
- Assign problem sets
- Evaluate student understanding

**Modification encouraged** - adapt templates for your courses.

---

## 🤝 Contributing

### Reporting Issues

- **Data quality problems:** Open issue with "data-quality" label
- **Methodological questions:** Open issue with "methods" label
- **Feature requests:** Open issue with "enhancement" label

### Contributing Real Data Notebooks

We welcome contributions of production notebooks with real data:

1. Fork repository
2. Create branch: `production/your-analysis`
3. Implement analysis with real data
4. Add data provenance badge
5. Pass peer review checklist
6. Submit pull request

**Requirements:**
- 100% real data (no simulation)
- Data provenance documentation
- Reproducibility from public APIs
- Grade A- or above (90+/100)

---

## 📜 License & Citation

### License
Apache 2.0 - See [LICENSE](LICENSE) for details.

### Citation

#### Template Notebooks (Simulated Data)
```bibtex
@software{kass_templates_2026,
  author = {Khipu Research},
  title = {KASS Causal Inference Templates},
  year = {2026},
  note = {Methodological demonstrations with simulated data},
  url = {https://github.com/KhipuResearch/KASS},
  version = {0.1.0}
}
```

#### Production Notebooks (Real Data)
```bibtex
@techreport{kass_production_2026,
  author = {Khipu Research},
  title = {[Notebook Title]: Real Data Analysis},
  institution = {Khipu Research},
  year = {2026},
  type = {Policy Analysis Report},
  url = {https://github.com/KhipuResearch/KASS/production/},
  note = {Grade A institutional certification}
}
```

---

## 📞 Contact

- **Email:** research@khipu.com
- **Issues:** https://github.com/KhipuResearch/KASS/issues
- **Discussions:** https://github.com/KhipuResearch/KASS/discussions

---

## 📚 Additional Resources

### Documentation
- [Real Data Remediation Plan](REAL_DATA_REMEDIATION_PLAN.md)
- [Institutional Audit Report](docs/INSTITUTIONAL_AUDIT_REPORT.md)
- [Data Quality Standards](docs/DATA_QUALITY_STANDARDS.md)
- [Peer Review Checklist](docs/PEER_REVIEW_CHECKLIST.md)

### Related Projects
- [KRL Data Connectors](https://github.com/KhipuResearch/krl-data-connectors)
- [KRL Model Zoo](https://github.com/KhipuResearch/KRL-Model-Zoo)
- [KRL Frameworks](https://github.com/KhipuResearch/krl-frameworks)

---

## 🎯 Roadmap

### Q1 2026
- ✅ Institutional audit completed
- ✅ Real data remediation plan created
- ✅ Repository reorganized (production/templates structure)
- 🚧 NB07 real data integration in progress

### Q2 2026
- 🎯 NB07 production release (A- grade)
- 🎯 NB20 real data integration

### Q3 2026
- 🎯 NB20 production release (A grade)
- 🎯 NB22 DUA negotiations with state agencies

### Q4 2026
- 🎯 NB22 production release (A grade)
- 🎯 Overall repository grade: A (95+/100)
- 🎯 Publication in peer-reviewed journal

---

## ⚖️ Legal & Compliance

### Data Use Agreements
Production notebooks using administrative data (e.g., state PIRL) operate under Data Use Agreements with strict confidentiality requirements. Aggregate results are published; microdata is not shared.

### Privacy Protection
All analyses with individual-level data comply with:
- Statistical disclosure controls
- Cell suppression (n < 10)
- Differential privacy where applicable

### Institutional Review
Analyses involving human subjects data undergo IRB review when required.

---

**Last Updated:** 2026-01-13
**Version:** 0.2.0 (Transition Phase)
**Maintained By:** Khipu Research Data Science Team

**🔗 Quick Links:**
- [Production Notebooks (Coming Soon)](production/)
- [Template Notebooks](templates/notebooks/)
- [Real Data Plan](REAL_DATA_REMEDIATION_PLAN.md)
- [Audit Report](docs/INSTITUTIONAL_AUDIT_REPORT.md)
