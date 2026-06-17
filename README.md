# Group1_ManalKabalan_AliAyash_HasanSerhan

AI4EO project on Agentic XAI for Earth Observation, covering paper selection, technical presentation, result reproduction, and project extension. Includes Random Forest, SHAP explainability, synthetic rice-yield reproduction, author-result comparison, wildfire classification, energy prediction regression, and decision-support experiments.

# AI4EO Agentic XAI Project

## Project Overview

This repository contains the full AI4EO course project on **Explainable AI (XAI) for Agentic AI**. The project follows the four main milestones: research paper selection, technical understanding and presentation, reproduction of experimental results, and project extension with additional analysis.

The selected work focuses on an **Agentic XAI approach**, where machine learning, SHAP explainability, and LLM-guided reasoning are combined to move from model explanation toward practical decision support.

The project began with a rice-yield prediction case study and was later extended to additional supervised tabular tasks, including wildfire classification and appliances energy prediction.

---

## Project Milestones

### Milestone 1: Research Paper Selection

A recent research paper related to **XAI for Agentic AI** was selected and reviewed. The selected paper provides a workflow that combines predictive modeling, explainability, and iterative reasoning to improve the quality of explanations and recommendations.

The selected paper was:

**Agentic Explainable Artificial Intelligence (Agentic XAI) Approach To Explore Better Explanation**

This paper was selected because it connects traditional XAI methods, especially SHAP, with LLM-based reasoning and iterative explanation refinement.

---

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

---

### Milestone 3: Reproduction of Experimental Results

The reproduction phase focused on rebuilding the main experimental workflow from the selected paper. This included:

* Environment setup
* Dataset preparation
* Random Forest model training
* Model evaluation
* SHAP-based explainability
* Generation of round-based visual analysis outputs
* Comparison between the author’s results and reproduced results

Since the original rice-yield dataset was not publicly available, a synthetic rice-yield dataset with the same expected structure was used. Therefore, the reproduction focused on the workflow structure rather than exact numerical replication.

---

## Author Results vs Reproduced Results

The author’s results were based on the original rice-yield dataset, while the reproduced results were generated using synthetic data. Because of this, numerical results such as R², RMSE, MAE, and SHAP values are different.

However, the main workflow was reproduced successfully:

* Same model type: Random Forest
* Same explainability method: SHAP
* Same round-based analysis structure
* Same type of visual outputs
* Same comparison logic between model performance and explanation quality

The main conclusion is that the project achieved **workflow reproduction**, not exact numerical replication.

---

### Milestone 4: Project Extension and Additional Results

The extension phase generalized the Agentic XAI workflow beyond the original rice-yield case study. The goal was to test whether the workflow could be adapted to new supervised tabular tasks with different domains, targets, and validation challenges.

Milestone 4 included two main extension tracks:

#### Track 1: Wildfire Classification

The first extension transferred the workflow from rice-yield regression to **wildfire classification** using an Earth Observation wildfire dataset.

This track included:

* Loading a wildfire dataset from `FiresDataset.parquet`
* Configuring a binary classification target
* Applying a spatial/group train-test split
* Training a Random Forest classifier
* Generating SHAP explanations
* Running refinement rounds for generalization, subgroup error, feature behavior, and robustness
* Identifying model weaknesses such as overfitting, low fire recall, subgroup instability, feature redundancy, and spatial generalization issues

The wildfire model was not suitable for operational decision support in its current form, but the Agentic XAI workflow successfully revealed where and why the model failed.

#### Track 2: Appliances Energy Prediction Regression

The second extension applied the generalized workflow to a real tabular regression dataset for **appliances energy prediction**.

This track included:

* Loading the appliances energy dataset
* Predicting continuous energy consumption
* Creating time-based features
* Training a Random Forest regressor
* Generating SHAP explanations
* Testing split sensitivity using random, grouped-date, and future-period validation
* Auditing subgroup errors and feature robustness

The random split produced moderate performance, but temporal validation showed that the model did not generalize well to future periods. This demonstrated the importance of validation design and showed how Agentic XAI can reveal overly optimistic baseline results.

---

## Repository Contents

```text
.
├── Task1_Research_Paper_Selection/
│   ├── selected paper
│   ├── project guidelines
│   └── paper selection materials
│
├── Task2_Technical_Understanding/
│   ├── technical presentation
│   └── paper analysis materials
│
├── Task3_Reproduction/
│   ├── 1-Original_Baseline_Synthesized_Data/
│   ├── 2-Ablation_Code_Synthesized_Data/
│   ├── 3-RiskFirst_Flip_Code_Synthesized_Data/
│   ├── 4-Original_Baseline_Duplicated_Synthesized_Data/
│   ├── reproduction notebook
│   ├── synthetic rice-yield dataset
│   ├── reproduced round-based outputs
│   └── reproduction report
│
├── Task4_Extension/
│   ├── Task4_Team1_1_Wildfire_Classification/
│   ├── Task4_Team1_2_Appliances_Energy_Prediction_Regression/
│   ├── Task4_FinalReport.pdf
│   ├── Task4_PPT.pdf
│   └── README.md
│
└── README.md
```

---

## General Methodology

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
Prompt and recommendation draft generation
        ↓
Validation, feasibility, robustness, and risk analysis
        ↓
Discussion of limitations and possible improvements
```

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* SHAP
* Matplotlib
* Seaborn
* Random Forest Regressor
* Random Forest Classifier
* Prompt-based LLM reasoning
* Jupyter Notebook

---

## Key Findings

The reproduced rice-yield results showed that the workflow can be executed successfully using a synthetic dataset. The performance values differ from the author’s results because the original dataset was unavailable, but the overall structure of the experiment was reproduced.

The Task 3 extension experiments showed that recommendation quality depends on evidence discipline, not simply the number of rounds. Stopping at Round 4 produced a more concise and defensible recommendation, while duplicate-data expansion inflated validation metrics because of data leakage.

The Task 4 extension showed that the Agentic XAI workflow can be generalized to new supervised tabular problems. In wildfire classification, the workflow revealed overfitting, low fire detection, subgroup failure, and unstable features. In appliances energy prediction, the workflow exposed that random validation was optimistic and that the model failed under future-period testing.

---

## Main Limitations

The main limitation of Milestone 3 was the use of a synthetic rice-yield dataset instead of the original dataset. Therefore, the numerical results should not be interpreted as exact agricultural findings.

The main limitation of Milestone 4 is that the generalized workflow is still a **human-in-the-loop Agentic XAI framework**, not a fully autonomous LLM agent. The notebook generates figures, diagnostics, prompts, and recommendation drafts, but automatic LLM self-reflection is not fully implemented.

The wildfire and energy models should not be presented as operational prediction systems. Their main value is diagnostic: they show how the Agentic XAI workflow can identify model weaknesses and guide future improvements.

---

## Conclusion

This project demonstrates the full AI4EO workflow for analyzing, reproducing, and extending a recent Agentic XAI study.

The project successfully reproduced the structure of the original rice-yield Agentic XAI workflow using synthetic data and extended the framework to additional tasks, including wildfire classification and appliances energy prediction.

The final outcome shows that Agentic XAI is valuable not only for explaining predictions, but also for validating model behavior, identifying weaknesses, detecting overfitting or leakage, and supporting more realistic decision-making.
