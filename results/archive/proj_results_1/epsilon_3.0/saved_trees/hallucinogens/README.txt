EXPERIMENT SUMMARY: HALLUCINOGENS

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0376

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.1221
RAPPOR-only F1:   0.0645
RAPPOR + DP-seg:  0.0729

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0575
  • DPseg  - Baseline: -0.0491

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.1219
RAPPOR-only logreg F1:   0.0646
RAPPOR + DP-seg logreg:  0.0729

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0572
  • DPseg  - Baseline: -0.0489

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      626
RAPPOR leaf count:        505
DP-seg leaf count:        30

Max depth:
  Baseline: 626
  RAPPOR:   505
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6472
  Baseline <-> DP-seg: 0.0226

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.013548
RAPPOR MI:   0.001232
DP-seg MI:   0.000096

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0909
  DP-seg / Baseline: 0.0071

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