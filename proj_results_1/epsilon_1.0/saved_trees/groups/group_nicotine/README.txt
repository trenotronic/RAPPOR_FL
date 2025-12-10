EXPERIMENT SUMMARY: NICOTINE

===========================================
DATASET
-------------------------------------------
Total samples: 115739
Positive prevalence: 0.2596

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.4968
RAPPOR-only F1:   0.3306
RAPPOR + DP-seg:  0.3093

F1 deltas (tree):
  • RAPPOR - Baseline: -0.1662
  • DPseg  - Baseline: -0.1875

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.4971
RAPPOR-only logreg F1:   0.3319
RAPPOR + DP-seg logreg:  0.3093

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.1652
  • DPseg  - Baseline: -0.1879

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      603
RAPPOR leaf count:        485
DP-seg leaf count:        30

Max depth:
  Baseline: 603
  RAPPOR:   485
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6432
  Baseline <-> DP-seg: 0.0235

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.058165
RAPPOR MI:   0.001896
DP-seg MI:   0.000102

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0326
  DP-seg / Baseline: 0.0018

===========================================
FILES
-------------------------------------------
baseline_tree.json
rappor_tree.json
dpseg_tree.json

baseline_tree_model.joblib
rappor_tree_model.joblib
dpseg_tree_model.joblib

baseline_logreg_model.joblib
rappor_logreg_model.joblib
dpseg_logreg_model.joblib

metadata.json

===========================================
NOTES
-------------------------------------------
Lower similarity scores indicate stronger
structural privacy effects.
Fewer leaves indicate reduced memorization risk.
Lower MI ratios indicate stronger privacy.