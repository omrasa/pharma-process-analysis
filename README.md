# Process Anomaly Detection — Manufacturing Sensor Data

## Overview
Statistical analysis of a real-world manufacturing process dataset to detect 
anomalies in sensor time-series data and investigate their relationship with 
production failures.

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

---

## Project Structure