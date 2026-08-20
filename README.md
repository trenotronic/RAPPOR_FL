
# From RAPPOR Noise to Usable Structure: Privacy-Preserving Decision Trees

**Author:** Bach Nguyen, Tren Meckel

This repository contains the full implementation and experimental results for the **From RAPPOR Noise to Usable Structure: Privacy-Preserving Decision Trees**, focusing on **RAPPOR**, **segmentation-based coarsening**, and **federated decision-tree evaluation**. The project analyzes how strong LDP affects predictive modeling for drug-use outcomes using the NSDUH 2021–2023 public-use dataset.

We benchmark three pipelines:

1. **Baseline (no privacy)**
2. **RAPPOR-only privatization**
3. **RAPPOR + DP Segmentation** (coarse binning prior to privatization)

We also sweep multiple feature resolutions, analyze global distribution distortion, measure mutual information leakage, and evaluate structural privacy by examining changes in learned tree shapes.

## **Project Overview**

RAPPOR provides strong user-level DP guarantees but introduces large distortion when features have high cardinality. To address this, we introduce a **segmentation-based coarsening layer** that reduces the categorical resolution from hundreds of categories to as few as 30–100 bins *before* applying RAPPOR.

This project evaluates whether segmentation can:

* **Restore utility** by reducing RAPPOR’s distortion
* **Maintain privacy** by lowering MI leakage
* **Preserve model structure** even under strong DP
* **Produce predictable, stable trees suitable for federated learning**

Experiments are conducted under **four privacy budgets**:
**ε ∈ {1.0, 3.0, 5.0, 10.0}**.

## **Repository Structure**

Here is an **updated README section** that cleanly incorporates the new `figures/` directory into the repository structure.
You can paste this **directly into your README.md** under the *Project Structure* section.

---

## **Project Structure**

The repository contains the full code pipeline, results, and all generated figures:

```text
Final_RAPPOR_FL.ipynb        # Main notebook containing full implementation
README.md                    # Project documentation
NSDUH_2021_2023_Tab.txt      # Combined NSDUH 2021–2023 dataset (tab-delimited)
requirements.txt             # Text file containing names of non-native Python libraries needed to run the code

figures/                     # All figures used in the final paper
├── cocaine/
├── crack/
├── hallucinogens/
├── heroin/
├── inhalants/
├── marijuana/
├── methamphetamine/
├── nicotine_vaping/
├── opioid_misuse/
├── pain_reliever_misuse/
├── sedative_misuse/
├── stimulant_misuse/
├── tobacco/
├── tranquilizer_misuse/
├── structure_similarity/    # Cross-epsilon tree similarity plots
└── summary/                 # Aggregate visualizations & global distortion figures

proj_results/                # Model artifacts and resolution-sweep outputs
├── epsilon_1.0/
│   ├── saved_trees/         # JSON tree structures + joblib models
│   │   ├── marijuana/
│   │   ├── cocaine/
│   │   ├── ../              # Other drugs
│   │   └── groups/
│   └── resolution_sweep/
│       ├── per_drug/        # F1, MI, JS vs. K for each outcome
│       ├── overall/         # Combined privacy–utility summaries
│       └── groups/          # Drug-group outcomes (illicit, nicotine, prescription)
├── epsilon_3.0/
├── epsilon_5.0/
└── epsilon_10.0/
```

### **Notes on the `figures/` Directory**

* Contains **all visual outputs** used in the paper and appendix.
* Each drug has a dedicated folder holding:

  * Resolution sweep plots (F1, MI, JS vs. K)
  * Model comparison plots (baseline vs RAPPOR vs DP-seg)
  * Tree shape similarity curves
  * Any diagnostic visualizations
* The `summary/` folder holds:

  * Global RAPPOR distortion plots
  * Cross-drug comparison figures
  * Tables turned into PNGs for paper inclusion

## **How to Run the Code**

### **1. Install Required Libraries**

All non-native libraries used in the project:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn joblib tqdm
pip install bitarray
```

Or simply:

```bash
pip install -r requirements.txt
```

### **2. Run the Notebook**

Open:

```
Final_RAPPOR_FL.ipynb
```

and execute all cells. All results (plots, trees, CSVs, model files) are automatically saved under `proj_results/`.

---

## **Major Design Decisions**

### **1. Segmentation-Based Coarsening**

To reduce distortion caused by privatizing high-cardinality categorical features, we compress each participant’s feature tuple:

```
(age, sex, race, education, poverty, distress)
```

into a **single categorical ID**, then further compress it to
**K ∈ {30, 50, 100, 200, 500, 639}** bins.

Benefits:

* Substantial reduction in RAPPOR distortion
* Stronger signal retention in decision trees
* Lower mutual information leakage
* Simple, interpretable category mapping

This coarsened representation feeds directly into the RAPPOR encoder.

### **2. RAPPOR Privatization Pipeline**

Each compressed category is transformed using:

* Bloom filter of size *k*
* *h* hash functions
* Permanent and instantaneous randomized response with parameter *p* and derived *q*

The decoder reconstructs an estimated categorical distribution from aggregated Bloom filters.

We evaluate:

* Distribution distortion (JS divergence)
* Category match rate
* MI leakage before/after segmentation

---

### **3. DP Segmentation (RAPPOR + Coarse Binning)**

Instead of applying RAPPOR directly to ~640 categories, we privatize a compressed representation. This:

* Reduces reconstruction error
* Recovers stable predictive patterns in trees
* Preserves ε-LDP
* Allows resolution sweeps to quantify privacy–utility tradeoffs

---

### **4. Predictive Models and Leakage Metrics**

For each drug outcome, we train:

* Decision tree (baseline, RAPPOR, DP-seg)
* Logistic regression versions of the same models

We evaluate:

* **F1 score** (primary utility metric)
* **Mutual information** (information leakage)
* **Tree structural leakage**:

  * Leaf count
  * Maximum depth
  * Shape similarity
* **Distribution distortion** via Jensen–Shannon divergence
* **Global RAPPOR distortion** independent of classification

---

## **Interpreting Results**

Key findings:

* **F1 is dominated by class imbalance**, especially for rare drugs.
* **RAPPOR collapses MI severely**, often reducing MI by 85–95%.
* **Segmentation partially restores MI** while keeping leakage extremely low.
* **DP-seg trees typically collapse to ~30 leaves**, showing low memorization risk.
* **Tree similarity decreases under DP**, indicating structural privacy.
* **Coarse resolutions (K ≤ 100) outperform fine resolutions**, even at high ε.
* **Global distribution distortion stabilizes around JS ≈ 0.40** across ε.

These results show that **coarse structure survives LDP**, whereas fine detail does not.

---

## **Libraries Used (Full List)**

```python
# Numerical & Data Handling
numpy
pandas
collections.Counter
math
hashlib

# File I/O & Logging
os
json
joblib
pathlib.Path

# Visualization
matplotlib
seaborn

# Machine Learning (scikit-learn)
sklearn.pipeline
sklearn.preprocessing.OneHotEncoder
sklearn.model_selection.train_test_split
sklearn.tree.DecisionTreeClassifier
sklearn.tree._tree
sklearn.tree
sklearn.linear_model.LogisticRegression
sklearn.metrics.f1_score
sklearn.metrics.mutual_info_score

# Privacy Utilities
bitarray (Bloom filters via custom code)
custom JS divergence + normalization functions
```

---

## **Reproducibility**

The entire pipeline is deterministic when seeds are fixed.
Re-running the notebook produces identical:

* Trees
* Performance metrics
* MI numbers
* JS divergence
* Resolution sweeps
* Structural leakage reports

All saved outputs can be inspected under `proj_results/`.
