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
RAPPOR-only F1:   0.0677
RAPPOR + DP-seg:  0.0719

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0544
  • DPseg  - Baseline: -0.0501

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.1219
RAPPOR-only logreg F1:   0.0676
RAPPOR + DP-seg logreg:  0.0719

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0543
  • DPseg  - Baseline: -0.0499

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      626
RAPPOR leaf count:        512
DP-seg leaf count:        30

Max depth:
  Baseline: 626
  RAPPOR:   512
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6659
  Baseline <-> DP-seg: 0.0226

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.013548
RAPPOR MI:   0.001423
DP-seg MI:   0.000070

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1050
  DP-seg / Baseline: 0.0052

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