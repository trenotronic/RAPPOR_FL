EXPERIMENT SUMMARY: HEROIN

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.0032

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: 4
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE
-------------------------------------------
Baseline accuracy:      0.9969
RAPPOR-only accuracy:   0.9969
RAPPOR + DP-seg:        0.9969

Accuracy deltas:
  • RAPPOR - Baseline: 0.0000
  • DPseg  - Baseline: 0.0000

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      15
RAPPOR leaf count:        15
DP-seg leaf count:        8

Max depth:
  Baseline: 5
  RAPPOR:   5
  DP-seg:   5

Tree shape similarity:
  Baseline <-> RAPPOR: 1.0000
  Baseline <-> DP-seg: 0.3750

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