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
Baseline accuracy:      0.0040
RAPPOR-only accuracy:   0.0000
RAPPOR + DP-seg:        0.0000

Accuracy deltas:
  • RAPPOR - Baseline: -0.0040
  • DPseg  - Baseline: -0.0040

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      15
RAPPOR leaf count:        14
DP-seg leaf count:        10

Max depth:
  Baseline: 5
  RAPPOR:   5
  DP-seg:   5

Tree shape similarity:
  Baseline <-> RAPPOR: 0.1667
  Baseline <-> DP-seg: 0.2632

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.067052
RAPPOR MI:   0.005322
DP-seg MI:   0.000091

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.0794
  DP-seg / Baseline: 0.0014

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