EXPERIMENT SUMMARY: SEDATIVE_MISUSE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0421

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.1228
RAPPOR-only F1:   0.0755
RAPPOR + DP-seg:  0.0765

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0473
  • DPseg  - Baseline: -0.0462

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.1230
RAPPOR-only logreg F1:   0.0751
RAPPOR + DP-seg logreg:  0.0765

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0480
  • DPseg  - Baseline: -0.0465

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      626
RAPPOR leaf count:        485
DP-seg leaf count:        30

Max depth:
  Baseline: 626
  RAPPOR:   485
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.5948
  Baseline <-> DP-seg: 0.0226

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.009880
RAPPOR MI:   0.001354
DP-seg MI:   0.000079

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1371
  DP-seg / Baseline: 0.0080

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