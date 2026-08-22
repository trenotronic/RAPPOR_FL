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
RAPPOR-only F1:   0.0247
RAPPOR + DP-seg:  0.0234

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0151
  • DPseg  - Baseline: -0.0164

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.0400
RAPPOR-only logreg F1:   0.0248
RAPPOR + DP-seg logreg:  0.0234

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0152
  • DPseg  - Baseline: -0.0166

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      253
RAPPOR leaf count:        514
DP-seg leaf count:        30

Max depth:
  Baseline: 253
  RAPPOR:   514
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.1969
  Baseline <-> DP-seg: 0.0542

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.005385
RAPPOR MI:   0.001509
DP-seg MI:   0.000057

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.2801
  DP-seg / Baseline: 0.0107

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