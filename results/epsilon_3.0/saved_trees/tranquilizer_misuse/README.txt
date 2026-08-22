EXPERIMENT SUMMARY: TRANQUILIZER_MISUSE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0986

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.2546
RAPPOR-only F1:   0.1616
RAPPOR + DP-seg:  0.1724

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0930
  • DPseg  - Baseline: -0.0822

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.2546
RAPPOR-only logreg F1:   0.1616
RAPPOR + DP-seg logreg:  0.1724

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0929
  • DPseg  - Baseline: -0.0822

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      621
RAPPOR leaf count:        504
DP-seg leaf count:        30

Max depth:
  Baseline: 621
  RAPPOR:   504
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6554
  Baseline <-> DP-seg: 0.0228

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.024263
RAPPOR MI:   0.001468
DP-seg MI:   0.000096

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0605
  DP-seg / Baseline: 0.0040

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