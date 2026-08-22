EXPERIMENT SUMMARY: PRESCRIPTION_MISUSE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.3195

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.4771
RAPPOR-only F1:   0.3868
RAPPOR + DP-seg:  0.3855

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0903
  • DPseg  - Baseline: -0.0917

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.4786
RAPPOR-only logreg F1:   0.3829
RAPPOR + DP-seg logreg:  0.3799

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0957
  • DPseg  - Baseline: -0.0987

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
Baseline MI: 0.023125
RAPPOR MI:   0.001512
DP-seg MI:   0.000089

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0654
  DP-seg / Baseline: 0.0039

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