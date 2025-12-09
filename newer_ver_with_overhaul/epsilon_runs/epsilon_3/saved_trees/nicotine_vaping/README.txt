EXPERIMENT SUMMARY: NICOTINE_VAPING

===========================================
DATASET
-------------------------------------------
Total samples: 115739
Positive prevalence: 0.1785

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: 4
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.3279
RAPPOR-only F1:   0.3027
RAPPOR + DP-seg:  0.2986

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0252
  • DPseg  - Baseline: -0.0293

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.4122
RAPPOR-only logreg F1:   0.2635
RAPPOR + DP-seg logreg:  0.2809

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.1487
  • DPseg  - Baseline: -0.1313

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      5
RAPPOR leaf count:        5
DP-seg leaf count:        5

Max depth:
  Baseline: 5
  RAPPOR:   5
  DP-seg:   5

Tree shape similarity:
  Baseline <-> RAPPOR: 1.0000
  Baseline <-> DP-seg: 1.0000

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.054836
RAPPOR MI:   0.002232
DP-seg MI:   0.000102

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0407
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