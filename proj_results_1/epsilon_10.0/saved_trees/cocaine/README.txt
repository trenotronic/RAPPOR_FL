EXPERIMENT SUMMARY: COCAINE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0194

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.0689
RAPPOR-only F1:   0.0368
RAPPOR + DP-seg:  0.0371

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0321
  • DPseg  - Baseline: -0.0319

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.0691
RAPPOR-only logreg F1:   0.0368
RAPPOR + DP-seg logreg:  0.0371

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0323
  • DPseg  - Baseline: -0.0320

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      623
RAPPOR leaf count:        513
DP-seg leaf count:        30

Max depth:
  Baseline: 623
  RAPPOR:   513
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6753
  Baseline <-> DP-seg: 0.0227

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.010133
RAPPOR MI:   0.001525
DP-seg MI:   0.000068

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1505
  DP-seg / Baseline: 0.0067

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