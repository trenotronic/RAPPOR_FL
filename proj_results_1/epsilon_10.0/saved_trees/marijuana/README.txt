EXPERIMENT SUMMARY: MARIJUANA

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.2363

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.4583
RAPPOR-only F1:   0.3160
RAPPOR + DP-seg:  0.3143

F1 deltas (tree):
  • RAPPOR - Baseline: -0.1423
  • DPseg  - Baseline: -0.1440

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.4585
RAPPOR-only logreg F1:   0.3167
RAPPOR + DP-seg logreg:  0.3201

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.1418
  • DPseg  - Baseline: -0.1384

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      630
RAPPOR leaf count:        515
DP-seg leaf count:        30

Max depth:
  Baseline: 630
  RAPPOR:   515
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6652
  Baseline <-> DP-seg: 0.0225

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.039295
RAPPOR MI:   0.001395
DP-seg MI:   0.000063

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0355
  DP-seg / Baseline: 0.0016

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