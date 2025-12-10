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
RAPPOR-only F1:   0.0180
RAPPOR + DP-seg:  0.0167

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0263
  • DPseg  - Baseline: -0.0276

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.0443
RAPPOR-only logreg F1:   0.0181
RAPPOR + DP-seg logreg:  0.0167

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0262
  • DPseg  - Baseline: -0.0277

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      627
RAPPOR leaf count:        485
DP-seg leaf count:        28

Max depth:
  Baseline: 627
  RAPPOR:   485
  DP-seg:   28

Tree shape similarity:
  Baseline <-> RAPPOR: 0.5928
  Baseline <-> DP-seg: 0.0211

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.008467
RAPPOR MI:   0.001563
DP-seg MI:   0.000064

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1847
  DP-seg / Baseline: 0.0076

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