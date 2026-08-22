EXPERIMENT SUMMARY: METHAMPHETAMINE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0086

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.0443
RAPPOR-only F1:   0.0179
RAPPOR + DP-seg:  0.0175

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0264
  • DPseg  - Baseline: -0.0268

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.0443
RAPPOR-only logreg F1:   0.0181
RAPPOR + DP-seg logreg:  0.0175

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0262
  • DPseg  - Baseline: -0.0268

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      627
RAPPOR leaf count:        511
DP-seg leaf count:        28

Max depth:
  Baseline: 627
  RAPPOR:   511
  DP-seg:   28

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6611
  Baseline <-> DP-seg: 0.0211

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.008467
RAPPOR MI:   0.001799
DP-seg MI:   0.000102

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.2125
  DP-seg / Baseline: 0.0120

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