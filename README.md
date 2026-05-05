# Process Anomaly Detection — Manufacturing Sensor Data

## Overview
Statistical analysis of a real-world manufacturing process dataset to detect
anomalies in sensor time-series data, investigate their relationship with
production failures, and support first-stage root cause analysis.

**Dataset:** SECOM semiconductor manufacturing dataset (UCI ML Repository)
**Scope:** 1,567 production runs · 590 process sensors · Pass/fail outcomes
**Tools:** Python · Pandas · NumPy · Matplotlib · Seaborn

---

## Key Findings

- **4.1% of production runs flagged as high-alert** using z-score anomaly detection
- **Fail runs show 50% higher anomaly scores** on average compared to pass runs (5.7 vs 3.8)
- **Failed runs are nearly 3x more likely** to exceed the alert threshold (9.6% vs 3.7%)
- **28 sensors dropped** due to >50% missing data — standard practice in regulated environments
- Anomaly detector provides actionable early-warning signal for process engineers
- **Root cause analysis:** Identified specific sensor clusters and production runs most
  associated with process failures — enabling targeted investigation

---

## Project Structure---

## Methods

**Data cleaning:** Column-wise median imputation for missing sensor values.
Columns with >50% missingness removed — a conservative threshold appropriate
for high-stakes manufacturing data.

**Anomaly detection:** Z-score based rule model. A sensor reading flagged as
anomalous if it exceeds 3 standard deviations from the column mean.
Per-run anomaly score = count of anomalous sensors in that run.
Alert threshold set at mean + 2 standard deviations of anomaly scores.

**Root cause analysis support:** Anomaly scores cross-referenced against
pass/fail labels to identify which production runs and sensor combinations
are most strongly associated with failures — the first stage of a structured
root cause investigation in a GMP-aligned environment.

**Validation:** Anomaly scores cross-referenced against pass/fail labels
to assess predictive relevance.

---

## Results

| Metric | Pass Runs | Fail Runs |
|---|---|---|
| Mean anomaly score | 3.8 | 5.7 |
| Max anomaly score | 45 | 52 |
| Above alert threshold | 3.7% | 9.6% |

---

## How to Run

```bash
git clone https://github.com/omrasa/pharma-process-analysis
cd pharma-process-analysis
pip install -r requirements.txt
jupyter notebook notebooks/
```

Download the SECOM dataset from the
[UCI ML Repository](https://archive.ics.uci.edu/dataset/179/secom)
and place `secom.data` and `secom_labels.data` in the `data/` folder.

---

## Background

This project applies statistical process monitoring and first-stage root
cause analysis techniques used in pharmaceutical and semiconductor
manufacturing — directly relevant to process analyst, quality, and
manufacturing data roles in regulated environments.