EXPERIMENT SUMMARY: HALLUCINOGENS

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0376

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: 4
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.0785
RAPPOR-only F1:   0.0725
RAPPOR + DP-seg:  0.0724

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0060
  • DPseg  - Baseline: -0.0062

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.1219
RAPPOR-only logreg F1:   0.0734
RAPPOR + DP-seg logreg:  0.0691

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0485
  • DPseg  - Baseline: -0.0528

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
Baseline MI: 0.013548
RAPPOR MI:   0.000353
DP-seg MI:   0.000074

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0260
  DP-seg / Baseline: 0.0055

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