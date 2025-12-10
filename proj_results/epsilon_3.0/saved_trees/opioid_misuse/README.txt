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
RAPPOR-only F1:   0.3082
RAPPOR + DP-seg:  0.2984

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0812
  • DPseg  - Baseline: -0.0911

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.3907
RAPPOR-only logreg F1:   0.3078
RAPPOR + DP-seg logreg:  0.2984

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0829
  • DPseg  - Baseline: -0.0923

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      625
RAPPOR leaf count:        504
DP-seg leaf count:        30

Max depth:
  Baseline: 625
  RAPPOR:   504
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6467
  Baseline <-> DP-seg: 0.0227

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.020121
RAPPOR MI:   0.001568
DP-seg MI:   0.000067

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0779
  DP-seg / Baseline: 0.0033

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