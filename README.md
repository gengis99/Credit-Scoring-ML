# Credit-Scoring-ML
Cost-sensitive credit scoring pipeline with threshold optimization under an approval-rate constraint (German Credit dataset)

## Project goal
Build a credit scoring model that estimates **P(BAD)** and turns it into an **operational approval/rejection policy** optimized for asymmetric error costs.

## Key idea
Instead of using a fixed threshold, the decision threshold **t** is selected on the **training set only** via cross-validation by minimizing:

**Cost(t) = FP(t) + 5 · FN(t)**  
subject to **approval rate ≥ 50%**.

## Main results (holdout test)
Final model: **LogReg_NO_SENS** with **t = 0.25**  
- Approval rate: **0.52**
- Bad rate among approved: **0.096**
- Recall (BAD): **0.833**
- Precision (BAD): **0.521**
- ROC-AUC: **0.803**
- PR-AUC: **0.651**


## Repository structure
- `report/` — PDF report + LaTeX sources  
- `images/` — figures used in the report  
- `src/` — scripts to reproduce training/evaluation (if provided)  

## Dataset
Statlog (German Credit Data), UCI Machine Learning Repository (url: https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data).  
Download from UCI and place it locally (not versioned in this repo).

## Reproducibility
All results and figures are reproducible from the provided scripts/notebooks (see `src/` / `notebooks/`).

## License
MIT
