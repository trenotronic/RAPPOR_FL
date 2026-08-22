EXPERIMENT SUMMARY: OPIOID_MISUSE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.2224

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.3894
RAPPOR-only F1:   0.3084
RAPPOR + DP-seg:  0.2875

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0810
  • DPseg  - Baseline: -0.1019

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.3907
RAPPOR-only logreg F1:   0.3086
RAPPOR + DP-seg logreg:  0.2875

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0821
  • DPseg  - Baseline: -0.1031

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      625
RAPPOR leaf count:        485
DP-seg leaf count:        29

Max depth:
  Baseline: 625
  RAPPOR:   485
  DP-seg:   29

Tree shape similarity:
  Baseline <-> RAPPOR: 0.5968
  Baseline <-> DP-seg: 0.0219

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.020121
RAPPOR MI:   0.001432
DP-seg MI:   0.000065

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0712
  DP-seg / Baseline: 0.0032

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