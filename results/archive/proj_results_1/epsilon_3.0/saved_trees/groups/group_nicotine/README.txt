EXPERIMENT SUMMARY: NICOTINE

===========================================
DATASET
-------------------------------------------
Total samples: 115739
Positive prevalence: 0.2596

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.4968
RAPPOR-only F1:   0.3290
RAPPOR + DP-seg:  0.3404

F1 deltas (tree):
  • RAPPOR - Baseline: -0.1678
  • DPseg  - Baseline: -0.1563

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.4971
RAPPOR-only logreg F1:   0.3282
RAPPOR + DP-seg logreg:  0.3404

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.1690
  • DPseg  - Baseline: -0.1567

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      603
RAPPOR leaf count:        504
DP-seg leaf count:        30

Max depth:
  Baseline: 603
  RAPPOR:   504
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6963
  Baseline <-> DP-seg: 0.0235

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.058165
RAPPOR MI:   0.002030
DP-seg MI:   0.000087

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0349
  DP-seg / Baseline: 0.0015

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