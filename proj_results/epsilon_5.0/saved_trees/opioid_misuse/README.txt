EXPERIMENT SUMMARY: OPIOID_MISUSE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.2224

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.3894
RAPPOR-only F1:   0.3152
RAPPOR + DP-seg:  0.3126

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0742
  • DPseg  - Baseline: -0.0768

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.3907
RAPPOR-only logreg F1:   0.3144
RAPPOR + DP-seg logreg:  0.3126

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0763
  • DPseg  - Baseline: -0.0780

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      625
RAPPOR leaf count:        510
DP-seg leaf count:        30

Max depth:
  Baseline: 625
  RAPPOR:   510
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6628
  Baseline <-> DP-seg: 0.0227

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.020121
RAPPOR MI:   0.001668
DP-seg MI:   0.000059

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0829
  DP-seg / Baseline: 0.0029

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