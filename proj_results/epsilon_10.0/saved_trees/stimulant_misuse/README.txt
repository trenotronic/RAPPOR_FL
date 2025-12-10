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
RAPPOR-only F1:   0.1382
RAPPOR + DP-seg:  0.1294

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0572
  • DPseg  - Baseline: -0.0660

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.1956
RAPPOR-only logreg F1:   0.1383
RAPPOR + DP-seg logreg:  0.1310

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0574
  • DPseg  - Baseline: -0.0647

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      632
RAPPOR leaf count:        514
DP-seg leaf count:        30

Max depth:
  Baseline: 632
  RAPPOR:   514
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6582
  Baseline <-> DP-seg: 0.0224

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.013577
RAPPOR MI:   0.001635
DP-seg MI:   0.000082

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1204
  DP-seg / Baseline: 0.0061

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