# Stablecoin Depegging Early Warning (PCA Framework)

## Overview
This repository implements a PCA-based anomaly detection framework for stablecoin depegging.  
It extracts latent factors and detects instability via z-score deviations.

---

## Structure

### Active Workflow
- raw_data/
- clean_data/

- data_cleaning.ipynb
- feature_engineering.ipynb

- stage_1/
- stage_2/
- stage_3/

### Reference (Not for Replication)
- _phase_1/ 
- _phase_2/

## Execution Order
- Data cleaning
- Feature engineering
- Stage 1: PCA (expanding + rolling)
- Stage 2: Out-of-sample evaluation
- Stage 3: Hybrid pooled PCA

## Outputs
- Stage 1: PCA scores, z-score signals, plots
- Stage 2: Loadings, variance tables, evaluation metrics, signals
- Stage 3: Outputs generated within notebook
