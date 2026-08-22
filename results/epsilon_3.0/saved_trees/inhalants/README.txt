EXPERIMENT SUMMARY: INHALANTS

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0125

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.0398
RAPPOR-only F1:   0.0227
RAPPOR + DP-seg:  0.0240

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0171
  • DPseg  - Baseline: -0.0158

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.0400
RAPPOR-only logreg F1:   0.0227
RAPPOR + DP-seg logreg:  0.0240

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0172
  • DPseg  - Baseline: -0.0160

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      253
RAPPOR leaf count:        504
DP-seg leaf count:        30

Max depth:
  Baseline: 253
  RAPPOR:   504
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.2019
  Baseline <-> DP-seg: 0.0542

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.005385
RAPPOR MI:   0.001470
DP-seg MI:   0.000060

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.2729
  DP-seg / Baseline: 0.0112

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