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
RAPPOR-only F1:   0.0178
RAPPOR + DP-seg:  0.0177

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0265
  • DPseg  - Baseline: -0.0266

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.0443
RAPPOR-only logreg F1:   0.0181
RAPPOR + DP-seg logreg:  0.0177

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0262
  • DPseg  - Baseline: -0.0267

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      627
RAPPOR leaf count:        514
DP-seg leaf count:        28

Max depth:
  Baseline: 627
  RAPPOR:   514
  DP-seg:   28

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6691
  Baseline <-> DP-seg: 0.0211

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.008467
RAPPOR MI:   0.001681
DP-seg MI:   0.000110

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1986
  DP-seg / Baseline: 0.0129

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