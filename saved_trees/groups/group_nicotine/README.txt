EXPERIMENT SUMMARY: NICOTINE

===========================================
DATASET
-------------------------------------------
Total samples: 115739
Positive prevalence: 0.2596

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: 4
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE
-------------------------------------------
Baseline accuracy:      0.7406
RAPPOR-only accuracy:   0.7404
RAPPOR + DP-seg:        0.7404

Accuracy deltas:
  • RAPPOR - Baseline: -0.0002
  • DPseg  - Baseline: -0.0002

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      15
RAPPOR leaf count:        15
DP-seg leaf count:        15

Max depth:
  Baseline: 5
  RAPPOR:   5
  DP-seg:   5

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6571
  Baseline <-> DP-seg: 0.2340

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.067052
RAPPOR MI:   0.005650
DP-seg MI:   0.000114

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0843
  DP-seg / Baseline: 0.0017

===========================================
FILES
-------------------------------------------
baseline_tree.json
rappor_tree.json
dpseg_tree.json
baseline_model.joblib
rappor_model.joblib
dpseg_model.joblib
metadata.json

===========================================
NOTES
-------------------------------------------
Lower similarity scores indicate stronger
structural privacy effects.
Fewer leaves indicate reduced memorization risk.
Lower MI ratios indicate stronger privacy.