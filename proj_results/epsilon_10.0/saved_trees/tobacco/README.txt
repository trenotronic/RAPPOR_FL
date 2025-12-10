EXPERIMENT SUMMARY: TOBACCO

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.1629

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.4021
RAPPOR-only F1:   0.2401
RAPPOR + DP-seg:  0.2464

F1 deltas (tree):
  • RAPPOR - Baseline: -0.1620
  • DPseg  - Baseline: -0.1557

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.4019
RAPPOR-only logreg F1:   0.2391
RAPPOR + DP-seg logreg:  0.2464

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.1627
  • DPseg  - Baseline: -0.1554

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      625
RAPPOR leaf count:        512
DP-seg leaf count:        30

Max depth:
  Baseline: 625
  RAPPOR:   512
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6681
  Baseline <-> DP-seg: 0.0227

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.054300
RAPPOR MI:   0.001395
DP-seg MI:   0.000062

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0257
  DP-seg / Baseline: 0.0011

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