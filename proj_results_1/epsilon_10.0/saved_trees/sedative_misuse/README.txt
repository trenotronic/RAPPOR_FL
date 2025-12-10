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
RAPPOR-only F1:   0.0767
RAPPOR + DP-seg:  0.0781

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0460
  • DPseg  - Baseline: -0.0447

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.1230
RAPPOR-only logreg F1:   0.0767
RAPPOR + DP-seg logreg:  0.0781

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0464
  • DPseg  - Baseline: -0.0450

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      626
RAPPOR leaf count:        515
DP-seg leaf count:        30

Max depth:
  Baseline: 626
  RAPPOR:   515
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6740
  Baseline <-> DP-seg: 0.0226

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.009880
RAPPOR MI:   0.001429
DP-seg MI:   0.000090

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1446
  DP-seg / Baseline: 0.0091

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