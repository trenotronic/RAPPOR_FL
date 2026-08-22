EXPERIMENT SUMMARY: STIMULANT_MISUSE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0796

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.1954
RAPPOR-only F1:   0.1369
RAPPOR + DP-seg:  0.1353

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0586
  • DPseg  - Baseline: -0.0602

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.1956
RAPPOR-only logreg F1:   0.1369
RAPPOR + DP-seg logreg:  0.1353

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0588
  • DPseg  - Baseline: -0.0604

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      632
RAPPOR leaf count:        505
DP-seg leaf count:        30

Max depth:
  Baseline: 632
  RAPPOR:   505
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6345
  Baseline <-> DP-seg: 0.0224

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.013577
RAPPOR MI:   0.001588
DP-seg MI:   0.000110

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1169
  DP-seg / Baseline: 0.0081

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