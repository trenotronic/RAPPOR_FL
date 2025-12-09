EXPERIMENT SUMMARY: METHAMPHETAMINE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0086

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: 4
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE
-------------------------------------------
Baseline accuracy:      0.9914
RAPPOR-only accuracy:   0.9914
RAPPOR + DP-seg:        0.9914

Accuracy deltas:
  • RAPPOR - Baseline: -0.0000
  • DPseg  - Baseline: -0.0000

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      16
RAPPOR leaf count:        11
DP-seg leaf count:        6

Max depth:
  Baseline: 5
  RAPPOR:   5
  DP-seg:   5

Tree shape similarity:
  Baseline <-> RAPPOR: 0.6250
  Baseline <-> DP-seg: 0.0769

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: nan
RAPPOR MI:   nan
DP-seg MI:   nan

MI ratios (relative to baseline):
  RAPPOR / Baseline: nan
  DP-seg / Baseline: nan

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