# Rigorous A/B Test Analysis: Beyond Statistical Significance

**Author:** Shlok Sheth | [Portfolio](https://shloksheth.netlify.app) | [LinkedIn](https://www.linkedin.com/in/shlok-sheth2016/)

---

## The Problem

A product team built a new engagement feature. The naive analyst checks p < 0.05 and calls it done.

This project shows what rigorous experiment analysis actually looks like — the kind that holds up in a product review, not just a notebook.

---

## What This Covers

| Step | What we do |
|------|-----------|
| Power analysis | Size the experiment before running it |
| SRM check | Verify the assignment mechanism is clean |
| Covariate balance | Confirm randomization is valid |
| CUPED | Reduce variance using pre-experiment data |
| Guardrail metrics | Check what the feature must not hurt |
| Segmentation | Find where the feature works best |
| Decision framework | Explicit launch/no-launch reasoning |

---

## Key Results

```
Sample per group:        25,000 users
Primary metric (CUPED):  +0.412 sessions/user  (p < 0.001)
Variance reduction:       0.9% via CUPED
Conversion lift:         +9.6%  (significant)
Revenue lift:            +$0.45 per user
Support tickets:         +6.9%  (not significant — guardrail holds)
Unsubscribe rate:         not significant — guardrail holds
Strongest segment:        25-34 age group (+0.431 sessions)
Decision:                LAUNCH
```

---

## Why Guardrails Matter

Statistical significance on the primary metric is not enough. A feature can move sessions up while quietly increasing support tickets or unsubscribes. Both guardrails were checked and held — that is what makes the launch recommendation credible.

---

## Project Structure

```
ab-test-portfolio/
├── data/
│   └── ab_test_data.csv           <- 50K user synthetic dataset
├── notebooks/
│   └── ab_test_analysis.ipynb     <- Full analysis notebook
├── figures/
│   ├── 01_pre_experiment_checks.png
│   ├── 02_power_analysis.png
│   ├── 03_primary_metric_sessions.png
│   ├── 04_guardrail_metrics.png
│   ├── 05_heterogeneous_effects.png
│   └── 06_summary_dashboard.png
├── requirements.txt
└── README.md
```

---

## Setup

```bash
git clone https://github.com/Shlok1375/ab-test-portfolio.git
cd ab-test-portfolio
pip install -r requirements.txt
jupyter notebook notebooks/ab_test_analysis.ipynb
```

---

## Requirements

```
pandas>=1.5
numpy>=1.23
matplotlib>=3.6
scipy>=1.9
jupyter>=1.0
```

---

## Limitations

1. Synthetic dataset — designed to mirror realistic product experiment structure but not real user data
2. CUPED assumes a linear relationship between the covariate and outcome
3. Segment analysis increases Type I error risk — results should be treated as directional, not confirmatory

---

*Part of my product data science portfolio. See [shloksheth.netlify.app](https://shloksheth.netlify.app) for more.*
