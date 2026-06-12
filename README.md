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
