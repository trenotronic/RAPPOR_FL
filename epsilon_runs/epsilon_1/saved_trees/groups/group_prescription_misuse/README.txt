EXPERIMENT SUMMARY: PRESCRIPTION_MISUSE

===========================================
DATASET
-------------------------------------------
Total samples: 173729
Positive prevalence: 0.3195

===========================================
MODEL CONFIGURATION
-------------------------------------------
Max depth: 4
DP segments (B): 30
Segment smoothing alpha: 0.7

===========================================
MODEL PERFORMANCE
-------------------------------------------
Baseline accuracy:      0.0000
RAPPOR-only accuracy:   0.0000
RAPPOR + DP-seg:        0.0000

Accuracy deltas:
  • RAPPOR - Baseline: 0.0000
  • DPseg  - Baseline: 0.0000

===========================================
STRUCTURAL LEAKAGE REPORT
-------------------------------------------
Baseline leaf count:      16
RAPPOR leaf count:        15
DP-seg leaf count:        9

Max depth:
  Baseline: 5
  RAPPOR:   5
  DP-seg:   5

Tree shape similarity:
  Baseline <-> RAPPOR: 0.5789
  Baseline <-> DP-seg: 0.2000

===========================================
INFORMATION LEAKAGE (MUTUAL INFORMATION)
-------------------------------------------
Baseline MI: 0.029147
RAPPOR MI:   0.003924
DP-seg MI:   0.000161

MI ratios (relative to baseline):
  RAPPOR / Baseline: 0.1346
  DP-seg / Baseline: 0.0055

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