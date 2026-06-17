# Group1_ManalKabalan_AliAyash_HasanSerhan
AI4EO project on Agentic XAI for Earth Observation, covering paper selection, technical presentation, result reproduction, and extension. Includes Random Forest, SHAP analysis, synthetic rice-yield data, author-result comparison, and decision-support experiments.

# AI4EO Agentic XAI Project

## Project Overview

This repository contains the full AI4EO course project on **Explainable AI (XAI) for Agentic AI**. The project follows the four main milestones: research paper selection, technical understanding and presentation, reproduction of experimental results, and project extension with additional analysis.

The selected work focuses on an **Agentic XAI approach for rice-yield prediction**, where machine learning, SHAP explainability, and LLM-guided reasoning are combined to move from model explanation toward practical decision support.

## Project Milestones

### Milestone 1: Research Paper Selection

A recent research paper related to **XAI for Agentic AI** was selected and reviewed. The selected paper provides a workflow that combines predictive modeling, explainability, and iterative reasoning to improve the quality of explanations and recommendations.

### Milestone 2: Technical Understanding and Presentation

The paper was studied in detail, including:

* The research problem
* The proposed Agentic XAI methodology
* The system workflow
* The explainability technique used
* The dataset and evaluation metrics
* The reported experimental results
* The strengths and limitations of the approach

A technical presentation was prepared to explain the motivation, methodology, implementation workflow, experimental setup, key findings, and limitations.

### Milestone 3: Reproduction of Experimental Results

The reproduction phase focused on rebuilding the main experimental workflow. This included:

* Environment setup
* Dataset preparation
* Random Forest model training
* Model evaluation
* SHAP-based explainability
* Generation of round-based visual analysis outputs
* Comparison between the author’s results and reproduced results

Since the original dataset was not publicly available, a synthetic rice-yield dataset with the same expected structure was used. Therefore, the reproduction focuses on the workflow structure rather than exact numerical replication.

## Author Results vs Reproduced Results

The author’s results were based on the original rice-yield dataset, while the reproduced results were generated using synthetic data. Because of this, numerical results such as R², RMSE, MAE, and SHAP values are different.

However, the main workflow was reproduced successfully:

* Same model type: Random Forest
* Same explainability method: SHAP
* Same round-based analysis structure
* Same type of visual outputs
* Same comparison logic between model performance and explanation quality

The main conclusion is that the project achieved **workflow reproduction**, not exact numerical replication.

## Milestone 4: Project Extension and Additional Results

The extension phase added further analysis beyond the basic reproduction. The additional results focused on validation, feasibility, risk, and decision-support interpretation.

The extended analysis includes:

* Scientific validation of model findings
* Feature importance stability
* Radiation4 partial dependence analysis
* Yield environment clustering
* Economic scenario analysis
* Feasibility assessment
* Decision-tree-based recommendation logic
* Risk and uncertainty analysis
* Technology adoption barriers
* Practical decision-support interpretation

This extension shows how Agentic XAI can move from technical model explanation toward more realistic agricultural and Earth Observation decision-making.

## Repository Contents

```text
.
├── notebooks/
│   └── PythonCode.ipynb
│
├── data/
│   └── synthetic rice-yield dataset
│
├── prompts/
│   ├── Prompt_1.txt
│   ├── Prompt_2.txt
│   └── Prompt_3.txt
│
├── results/
│   ├── reproduced analysis PDFs
│   ├── round-based outputs
│   └── comparison figures
│
├── reports/
│   ├── reproduction report
│   └── extension report
│
├── presentations/
│   └── project presentation
│
└── README.md
```

## Methodology

The implemented workflow follows these main steps:

```text
Dataset preparation
        ↓
Random Forest model training
        ↓
Model evaluation
        ↓
SHAP explanation
        ↓
Round-based visual analysis
        ↓
LLM-guided interpretation using prompts
        ↓
Recommendation refinement
        ↓
Validation, feasibility, and risk analysis
```

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* SHAP
* Matplotlib
* Seaborn
* Random Forest Regressor
* Prompt-based LLM reasoning

## Key Findings

The reproduced results show that the workflow can be executed successfully using a synthetic dataset. The performance values differ from the author’s results because the original dataset was unavailable, but the overall structure of the experiment was reproduced.

The extended analysis also shows that Agentic XAI is useful because it does not stop at explaining model predictions. It supports validation, practical planning, feasibility checking, and risk-aware decision support.

## Main Limitation

The main limitation is the use of a synthetic dataset instead of the original rice-yield dataset. As a result, the numerical results should not be interpreted as exact agricultural findings. They are used to validate and demonstrate the reproducibility of the workflow.

## Conclusion

This project demonstrates the full AI4EO workflow for analyzing, reproducing, and extending a recent Agentic XAI study. The repository documents the selected paper, technical understanding, reproduction process, comparison with author results, and additional extension experiments.

The final outcome shows that the Agentic XAI workflow can be reproduced structurally and extended toward practical Earth Observation decision support, even when exact numerical replication is limited by dataset availability.
# Task 4 — Project Extension and Additional Results

## Overview

This folder contains the materials related to **Task 4 / Milestone 4** of the AI4EO course project. The objective of this task was to extend the Agentic XAI workflow beyond the original rice-yield reproduction and test whether the framework can generalize to new supervised tabular problems.

The extension focused on applying the generalized Agentic XAI workflow to two different experimental tracks:

1. **Wildfire Classification**
2. **Appliances Energy Prediction Regression**

The goal was not only to improve prediction performance, but also to evaluate whether the Agentic XAI workflow can reveal model weaknesses, validation problems, subgroup errors, feature instability, and limitations.

---

## Purpose of Task 4

The purpose of Task 4 was to:

* Extend the original Agentic XAI workflow beyond rice-yield prediction.
* Generalize the notebook so it is not fixed to one dataset, target, or domain.
* Test both classification and regression tasks.
* Apply SHAP explainability to new datasets.
* Generate evidence-based refinement rounds.
* Evaluate model reliability under stronger validation settings.
* Identify practical limitations and possible improvements.

---

## Folder Contents

This task folder contains:

```text
Task4_Team1_1_Wildfire_Classification/
Task4_Team1_2_Appliances_Energy_Prediction_Regression/
README.md
Task4_FinalReport.pdf
Task4_PPT.pdf
```

---

# Track 1 — Wildfire Classification

## Objective

The first extension transferred the Agentic XAI workflow from rice-yield regression to **wildfire classification** using Earth Observation wildfire data.

The main question was:

```text
Can the Agentic XAI workflow be generalized from rice-yield regression to wildfire classification?
```

## Dataset

The wildfire experiment used:

```text
Dataset: FiresDataset.parquet
Rows: 173,991
Columns: 51
Target: Fire_Label
Task type: Binary classification
```

The dataset included wildfire-related Earth Observation, weather, terrain, and land-cover variables.

## Experimental Setup

The wildfire workflow included:

* Configurable dataset loading.
* Binary target selection.
* Spatial/group train-test split using X and Y coordinates.
* Random Forest classifier training.
* SHAP explainability.
* Round-based diagnostic analysis.
* Prompt and recommendation draft generation.

The model used:

```text
Model: Random Forest Classifier
Number of trees: 300
Validation: Spatial/group split
SHAP: Approximate TreeSHAP on 500 test samples
```

## Wildfire Results

The new generalized wildfire model achieved:

```text
Accuracy: 0.5687
Balanced Accuracy: 0.5837
Precision: 0.6722
Recall: 0.3891
F1 Score: 0.4929
ROC-AUC: 0.6892
```

The most important result is the low recall:

```text
Recall = 0.3891
```

This means the model detected fewer than 4 out of every 10 fire cases, which makes it unsuitable for operational wildfire decision support in its current form.

## Wildfire SHAP Findings

The strongest SHAP features were:

* Elevation__Low
* Elevation
* Aspect
* LUC_majori
* Slope

This confirms that the generalized workflow adapted to wildfire-related terrain and land-cover variables instead of relying on rice-specific variables such as Radiation4.

## Wildfire Refinement Rounds

The wildfire workflow generated several evidence stages:

### Round 0 — Baseline Performance and SHAP

The model was trained and evaluated, and SHAP was used to identify the most influential wildfire-related features.

### Round 1 — Generalization and Calibration

The model showed severe overfitting. Training balanced accuracy was almost perfect, while test balanced accuracy remained weak.

### Round 2 — Error, Subgroup, and Spatial Audit

The subgroup analysis showed that some terrain and elevation groups had much higher error rates than others.

### Round 3 — Feature Behavior and Co-Movement

The workflow detected overlap between categorical elevation bands and numeric elevation values, showing possible feature redundancy.

### Round 4 — Robustness and Sensitivity

Permutation testing showed that elevation-related features were important, while Aspect appeared unstable under the spatial holdout.

## Wildfire Conclusion

The wildfire extension was successful at the **workflow level**, but not at the **model-performance level**.

The correct interpretation is:

```text
Framework: successful
Wildfire model: weak
Main value: diagnostic
Operational readiness: not ready
```

The Agentic XAI workflow helped identify overfitting, low fire recall, subgroup failure, feature redundancy, calibration weakness, and unstable feature behavior.

---

# Track 2 — Appliances Energy Prediction Regression

## Objective

The second extension applied the generalized Agentic XAI workflow to a real tabular regression dataset for **appliances energy prediction**.

The main question was:

```text
Can the generalized Agentic XAI workflow handle a real non-rice regression dataset?
```

## Dataset

The appliances energy experiment used:

```text
Dataset: energydata_complete.csv
Rows: 19,735
Original columns: 29
Target: Appliances
Task type: Regression
```

The dataset includes appliance energy consumption, indoor climate variables, outdoor weather variables, lighting, and time information.

## Experimental Setup

The appliances energy workflow included:

* Dataset loading.
* Target selection.
* Date handling and time-based feature engineering.
* Random Forest regression.
* SHAP explanation.
* Split sensitivity testing.
* Subgroup error analysis.
* Feature behavior and co-movement analysis.
* Robustness testing.
* Prompt and recommendation draft generation.

The model used:

```text
Model: Random Forest Regressor
Number of trees: 300
Primary split: Random 80/20 split
Additional validation: Grouped-date and future-period stress tests
SHAP: 1,000 held-out samples
```

## Appliances Energy Results

The random-row split produced moderate performance:

```text
Train R²: 0.9461
Random-row Test R²: 0.6171
RMSE: 61.9039
MAE: 29.1678
```

However, stronger validation revealed serious weaknesses:

```text
Random split R²: 0.6171
Grouped-date split R²: -0.0527
Future-period split R²: -3.6599
```

This means the model looked acceptable under random validation but failed when tested on separated dates or future data.

## Appliances SHAP Findings

The strongest SHAP features were mainly related to time and household activity, including:

* date_time_sin
* date_time_cos
* lights
* date_week_sin
* pressure
* room temperature
* room humidity

This shows that the model learned schedule and behavior patterns, not only environmental relationships.

## Appliances Refinement Rounds

### Round 0 — Baseline Regression and SHAP

The model was trained using a random split, and SHAP showed that time-based and lighting features strongly influenced predictions.

### Round 1 — Split Sensitivity

The workflow tested random, grouped-date, and future-period validation. This was the most important stage because it showed that the random split was overly optimistic.

### Round 2 — Subgroup Error Audit

The model produced higher errors during active household conditions, especially when lighting values were higher.

### Round 3 — Feature Behavior and Co-Movement

The workflow showed strong relationships between cyclical time features, such as date_time_sin and date_time_cos.

### Round 4 — Robustness and Explanation Stability

Permutation testing showed that the model depended heavily on time-derived features, especially date_time_cos and date_time_sin.

## Appliances Energy Conclusion

The appliances energy extension was successful at the **workflow level**, but the model should not be presented as a reliable future forecasting system.

The correct interpretation is:

```text
Random validation: moderate performance
Temporal validation: failed
Main issue: temporal leakage and weak future generalization
Main value: diagnostic
```

The Agentic XAI workflow helped reveal that the original random split was too optimistic and that future-period validation is necessary before making forecasting claims.

---

## Agentic XAI Status

Task 4 implements a **generalized human-in-the-loop Agentic XAI framework**.

The workflow supports:

* Evidence-driven module selection.
* Round-specific figures and tables.
* SHAP explanation.
* Prompt generation.
* Recommendation draft generation.
* Diagnostic refinement across multiple rounds.

However, the workflow does **not** yet implement a fully autonomous LLM loop.

The LLM status is:

```text
Prompt generation: implemented
Recommendation drafts: implemented
Automatic LLM reflection: not active
Closed-loop autonomous refinement: not complete
```

Therefore, the correct claim is:

```text
Task 4 implements a generalized human-in-the-loop Agentic XAI framework, not a fully autonomous agent.
```

---

## Key Findings

The main findings of Task 4 are:

* The Agentic XAI workflow can be generalized beyond rice-yield prediction.
* The workflow supports both classification and regression tasks.
* The wildfire model failed under spatial generalization, but the framework revealed why.
* The appliances model performed moderately under random split but failed under temporal validation.
* SHAP explanations adapted to each domain and identified different important features.
* The framework is useful for diagnosing model failure, not only for explaining successful models.
* Strong validation design is essential before making operational claims.

---

## Main Limitations

The main limitations are:

* The wildfire model is not ready for operational fire-risk decision support.
* The appliances model is not reliable for future energy forecasting.
* The framework currently focuses on supervised tabular datasets.
* Image, text, unsupervised, and arbitrary multiclass tasks require further extension.
* The LLM loop is manual and human-in-the-loop, not fully autonomous.
* SHAP was computed on sampled test rows for practical local execution.

---

## Recommended Future Work

Future improvements include:

* Repeating wildfire validation with a fair reference comparison.
* Testing additional wildfire models and regularized configurations.
* Encoding circular variables such as Aspect using sine and cosine.
* Applying grouped or spatial cross-validation.
* Using rolling or expanding-window validation for time-series regression.
* Comparing Random Forest with simpler baselines.
* Completing the LLM loop using one fixed model, prompt configuration, and evaluation rubric.
* Adding multiple reviewers to score recommendation quality.

---

## Conclusion

Task 4 successfully extended the Agentic XAI workflow beyond the original rice-yield reproduction.

The wildfire classification experiment showed that the framework can transfer to an Earth Observation classification problem and reveal overfitting, subgroup failure, and low fire detection.

The appliances energy prediction experiment showed that the same framework can transfer to a real regression dataset and expose validation sensitivity, temporal leakage, and poor future generalization.

Overall, Task 4 demonstrates that Agentic XAI is valuable not only when models perform well, but also when models fail, because it helps explain where the failure happens, why it happens, and what should be tested next.
