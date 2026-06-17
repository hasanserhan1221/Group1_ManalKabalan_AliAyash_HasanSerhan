# Task 3 — Reproduction of Experimental Results

## Overview

This folder contains the materials related to **Task 3 / Milestone 3** of the AI4EO course project. The objective of this task was to reproduce the main experimental workflow of the selected paper:

**Agentic Explainable Artificial Intelligence (Agentic XAI) Approach To Explore Better Explanation**

The reproduction focused on rebuilding the rice-yield prediction workflow using Random Forest, SHAP explainability, round-based outputs, and comparison with the author’s original results.

## Purpose of Task 3

The purpose of this task was to:

* Set up and run the provided notebook.
* Prepare a dataset compatible with the notebook.
* Train a Random Forest model for rice-yield prediction.
* Generate SHAP explanations and visual outputs.
* Reproduce the round-based analysis workflow.
* Compare the reproduced results with the author’s original outputs.
* Discuss differences, challenges, and limitations.

## Dataset Used

The original rice-yield dataset was not publicly available in the supplementary materials. It was available only upon request, and no response was received before the reproduction deadline.

Because of this, a **synthetic rice-yield dataset** was created with the same expected structure as the original notebook input.

The synthetic dataset included:

* Yield target variable
* Weather variables
* Radiation variables
* Temperature variables
* Precipitation variables
* Soil chemistry variables
* Soil physical variables
* Agricultural management variables

The reproduction therefore focuses on **workflow reproduction**, not exact numerical replication.

## Reproduction Workflow

The main reproduction workflow was:

```text
Load synthetic rice-yield dataset
        ↓
Prepare features and target
        ↓
Train Random Forest Regressor
        ↓
Evaluate model performance
        ↓
Calculate SHAP values
        ↓
Generate round-based PDF outputs
        ↓
Compare reproduced outputs with author outputs
        ↓
Analyze limitations and differences
```

## Folder Contents

This task folder contains the following experiment folders:

```text
1-Original_Baseline_Synthesized_Data/
2-Ablation_Code_Synthesized_Data/
3-RiskFirst_Flip_Code_Synthesized_Data/
4-Original_Baseline_Duplicated_Synthesized_Data/
```

### 1-Original_Baseline_Synthesized_Data

This folder contains the baseline reproduction using the synthetic rice-yield dataset. It reproduces the main notebook workflow and generates the same type of round-based outputs as the original author results.

### 2-Ablation_Code_Synthesized_Data

This folder contains the **Stop-at-Round-4 ablation experiment**. The objective was to test whether stopping the Agentic XAI refinement process at Round 4 gives a more reliable and concise recommendation than continuing until Round 10.

The result showed that stopping at Round 4 produced the most defensible recommendation because it stayed closer to available evidence and avoided later speculative expansion.

### 3-RiskFirst_Flip_Code_Synthesized_Data

This folder contains the **Risk-First Ordering experiment**. The objective was to test whether introducing risk analysis earlier in the workflow changes the final recommendation.

The result showed that simply reordering static evidence did not meaningfully change the final decision. Effective improvement would require dynamic re-evaluation after each round.

### 4-Original_Baseline_Duplicated_Synthesized_Data

This folder contains the **Duplicate-Data Validation Stress Test**. The objective was to test whether increasing dataset size through duplicated records improves model performance.

The result showed that duplication artificially inflated validation scores because identical samples leaked between training and validation folds. This demonstrated that higher validation performance was caused by data leakage, not true model improvement.

## Main Reproduced Results

The reproduction successfully generated the full round-based Agentic XAI workflow from Round 0 to Round 10.

Key results included:

* Random Forest model training
* SHAP feature importance
* SHAP beeswarm plots
* Growth-stage analysis
* Residual analysis
* PCA analysis
* Scientific validation
* Economic analysis
* Feasibility analysis
* Risk assessment
* Final decision-support framework

The reproduced model achieved:

```text
Training R² = 0.895
Cross-validation R² = 0.221
RMSE = 0.163
MAE = 0.134
```

The lower validation score shows that the synthetic dataset did not capture the same predictive relationships as the original dataset.

## Author Results vs Reproduced Results

The author’s results were produced using the original rice-yield dataset, while our reproduced results were generated using synthetic data. Therefore, the exact numerical values are different.

However, the main workflow structure was reproduced successfully:

* Same model type: Random Forest Regressor
* Same explainability method: SHAP
* Same round-based output structure
* Same type of visual analysis
* Same comparison between model explanation and recommendation quality

The reproduced outputs follow the same analytical template as the author outputs, but the numerical results differ because the dataset is different.

## Additional Experiments

Task 3 also included additional experimental tests beyond the baseline reproduction.

### Experiment 1 — Stop-at-Round-4 Ablation

This experiment tested whether stopping the Agentic XAI process at Round 4 improves recommendation quality.

Result:

```text
Recommendation Quality Score = 28/35
```

This was the best-performing strategy because early stopping reduced over-refinement and kept the recommendation more evidence-grounded.

### Experiment 2 — Risk-First Ordering Test

This experiment tested whether moving risk analysis earlier changes the final recommendation.

Result:

```text
Recommendation Quality Score = 16/35
```

The final decision remained mostly unchanged, showing that reordering static evidence alone is not enough.

### Experiment 3 — Duplicate-Data Validation Stress Test

This experiment tested whether duplicating the synthetic dataset improves performance.

Result:

```text
Baseline LOOCV R² = 0.2215
Duplicated ×2 LOOCV R² = 0.6685
Duplicated ×4 LOOCV R² = 0.9603
```

The increase was not real improvement. It was caused by validation leakage, where duplicate records appeared in both training and validation folds.

## Key Findings

The main findings of Task 3 were:

* The Agentic XAI workflow was successfully reproduced structurally.
* Exact numerical replication was not possible because the original dataset was unavailable.
* Radiation4 remained an important SHAP feature in the reproduced workflow.
* The synthetic model had much weaker validation performance than the author’s original model.
* Stopping at Round 4 produced the most stable and evidence-grounded recommendation.
* Risk-first ordering did not improve the final recommendation.
* Duplicate-data expansion created misleading validation improvement due to leakage.

## Main Limitation

The main limitation of Task 3 is the use of a synthetic dataset instead of the original rice-yield dataset. As a result, the reproduced results should not be interpreted as exact scientific or agricultural findings.

The reproduction validates the workflow, notebook execution, and output structure, but not the exact original numerical performance.

## Materials Included

This task folder may include:

```text
Reproduction notebook
Synthetic rice-yield dataset
Generated round-based outputs
Baseline reproduction results
Stop-at-Round-4 ablation experiment
Risk-first ordering experiment
Duplicated-data stress test
Task3_PPT.pdf
ReproductionReport_Task3.pdf
```

## Conclusion

Task 3 successfully reproduced the structure of the selected Agentic XAI workflow using a synthetic rice-yield dataset. The notebook generated the same types of outputs as the author’s original round-based workflow, including model evaluation, SHAP explanations, agronomic interpretation, decision support, risk assessment, and final recommendation analysis.

The task confirmed that the workflow can be reproduced, but the exact numerical results cannot be replicated without the original dataset. The additional experiments also showed that recommendation quality depends on evidence discipline, and model performance depends on data integrity rather than artificial data expansion.
