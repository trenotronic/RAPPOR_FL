EXPERIMENT SUMMARY: PAIN_RELIEVER_MISUSE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.2217

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: None
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE (Decision Tree, F1)
-------------------------------------------
Baseline F1:      0.3905
RAPPOR-only F1:   0.3008
RAPPOR + DP-seg:  0.3194

F1 deltas (tree):
  • RAPPOR - Baseline: -0.0896
  • DPseg  - Baseline: -0.0711

===========================================
MODEL PERFORMANCE (Logistic Regression, F1)
-------------------------------------------
Baseline logreg F1:      0.3909
RAPPOR-only logreg F1:   0.3009
RAPPOR + DP-seg logreg:  0.3194

F1 deltas (logreg):
  • RAPPOR - Baseline: -0.0900
  • DPseg  - Baseline: -0.0715

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      628
RAPPOR leaf count:        505
DP-seg leaf count:        30

Max depth:
  Baseline: 628
  RAPPOR:   505
  DP-seg:   30

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6430
  Baseline <-> DP-seg: 0.0226

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.019852
RAPPOR MI:   0.001517
DP-seg MI:   0.000073

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0764
  DP-seg / Baseline: 0.0037

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