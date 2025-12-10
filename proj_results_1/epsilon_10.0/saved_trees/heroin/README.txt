EXPERIMENT SUMMARY: HEROIN

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0032

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.0164
RAPPOR-only F1:   0.0062
RAPPOR + DP-seg:  0.0063

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0102
  • DPseg  - Baseline: -0.0102

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.0161
RAPPOR-only logreg F1:   0.0063
RAPPOR + DP-seg logreg:  0.0063

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0099
  • DPseg  - Baseline: -0.0099

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      623
RAPPOR leaf count:        513
DP-seg leaf count:        29

Max depth:
  Baseline: 623
  RAPPOR:   513
  DP-seg:   29

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6753
  Baseline <-> DP-seg: 0.0220

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.004382
RAPPOR MI:   0.001469
DP-seg MI:   0.000097

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.3351
  DP-seg / Baseline: 0.0220

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