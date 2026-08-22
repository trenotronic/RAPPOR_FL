EXPERIMENT SUMMARY: ILLICIT

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.2487

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.4670
RAPPOR-only F1:   0.3385
RAPPOR + DP-seg:  0.3404

F1 deltas (tree):
  • RAPPOR - Baseline: -0.1286
  • DPseg  - Baseline: -0.1266

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.4670
RAPPOR-only logreg F1:   0.3378
RAPPOR + DP-seg logreg:  0.3404

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.1292
  • DPseg  - Baseline: -0.1266

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      627
RAPPOR leaf count:        505
DP-seg leaf count:        30

Max depth:
  Baseline: 627
  RAPPOR:   505
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6451
  Baseline <-> DP-seg: 0.0226

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.038762
RAPPOR MI:   0.001492
DP-seg MI:   0.000076

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0385
  DP-seg / Baseline: 0.0019

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