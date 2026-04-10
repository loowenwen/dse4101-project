# Stablecoin Depegging Early Warning (PCA Framework)

## Overview
This repository investigates early warning signals for **stablecoin depegging** using a PCA-based anomaly detection framework.

Stablecoin depegging events are rare, heterogeneous, and often driven by complex market dynamics. Instead of treating the problem as a traditional prediction task, this project frames it as an **unsupervised anomaly detection problem**, where deviations from normal market conditions are identified in a latent factor space.

The project develops and evaluates a **three-stage PCA framework** to examine:
- whether instability signals exist,
- whether they generalise over time,
- and whether they extend across different stablecoin designs.

**Stablecoins studied:**
- Algorithmic: UST  
- Crypto-collateralised: DAI  
- Fiat-backed: USDC, USDT, USDP (PAX)  

---

## Repository Structure

### Active Workflow (Used in Final Analysis)
- `raw_data/`  
  Raw input datasets (price, volume, macro variables)

- `clean_data/`  
  Processed datasets (`*_clean.parquet`, `*_final.parquet`)

- `data_cleaning.ipynb`  
  Cleans and aligns raw datasets

- `feature_engineering.ipynb`  
  Constructs features and depegging labels

- `stage_1/`  
  Exploratory PCA (rolling + expanding windows)

- `stage_2/`  
  Out-of-sample PCA validation (global + custom split)

- `stage_3/`  
  Hybrid pooled PCA across stablecoin types

---

### Reference (Not Required for Replication)
- `_phase_1/`  
- `_phase_2/`  

These folders contain earlier exploratory work and are not part of the final pipeline.

---

## Methodology Overview

The project follows a **three-stage empirical framework**:

### Stage 1: Exploratory Detection
- Rolling and expanding PCA  
- Detects abnormal deviations in latent factor space  
- Focus: identifying early warning signals  

### Stage 2: Out-of-Sample Validation
- Fixed PCA trained on historical data  
- Applied to unseen test data  
- Focus: time generalisation of signals  

### Stage 3: Cross-Type Analysis
- Hybrid pooled PCA across stablecoin types  
- Uses reconstruction error for anomaly detection  
- Focus: structural generalisation across designs  

---

## Execution Order

To reproduce the analysis:

1. Run `data_cleaning.ipynb`  
2. Run `feature_engineering.ipynb`  
3. Run Stage 1 notebooks (rolling / expanding PCA)  
4. Run Stage 2 notebooks (global split / custom split)  
5. Run Stage 3 notebook (hybrid pooled PCA)  

---

## Outputs

### Stage 1
- PCA scores and z-score signals  
- Rolling/expanding window plots  
- Early warning signal analysis  

### Stage 2
- Out-of-sample PCA loadings  
- Evaluation metrics (precision, recall, F1)  
- Signal plots and performance tables  

### Stage 3
- Reconstruction error-based anomaly signals  
- Cross-type comparison results  
- Outputs generated within notebook  

---

## Notes
- The workflow is **not fully automated** and requires manual execution of notebooks.  
- Some parameters (e.g. stablecoin selection, window size, split dates) must be manually adjusted.  
- Certain outputs may require uncommenting save commands in notebooks.  

---

## Course Context
This project was completed as part of **DSE4101: Capstone Project in Data Science and Economics I**, focusing on applications in **digital currencies and financial instability analysis**.