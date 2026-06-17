# Task 2 — Technical Understanding and Presentation

## Overview

This folder contains the materials related to **Task 2 / Milestone 2** of the AI4EO course project. The objective of this task was to study and explain the selected paper, understand its methodology, and prepare a technical presentation about the Agentic XAI workflow.

## Selected Paper

The selected paper is:

**Agentic Explainable Artificial Intelligence (Agentic XAI) Approach To Explore Better Explanation**

The paper proposes a workflow that combines machine learning, SHAP explainability, and LLM-guided reasoning to improve the communication of AI-generated explanations.

## Purpose of Task 2

The purpose of this task was to understand and present:

* The motivation behind the paper.
* The Agentic XAI methodology.
* The system architecture.
* The role of Random Forest and SHAP.
* The role of the LLM in explanation refinement.
* The dataset and evaluation metrics.
* The main experimental findings.
* The limitations and design principles of the approach.

## Presentation Summary

The presentation explains that traditional XAI outputs, such as SHAP plots, can be technical and difficult for non-experts to understand. The selected paper addresses this problem by using an LLM as a second explanation layer that translates SHAP results into clearer explanations, counterfactual scenarios, and practical recommendations.

The presentation also explains why the workflow is considered **Agentic AI**. Instead of stopping after one explanation, the system runs multiple refinement rounds. In each round, the LLM reviews the previous explanation, identifies missing analysis, suggests new evidence, and refines the recommendation.

## Main Topics Covered

The presentation covers the following topics:

1. **Introduction and Motivation**
   The goal is to improve the communication of AI-generated insights so they are understandable and useful for human decision-makers.

2. **Agentic XAI Workflow**
   The workflow starts with SHAP analysis and then uses an LLM to iteratively improve explanations across multiple rounds.

3. **System Architecture**
   The architecture includes agricultural tabular data, a Random Forest model, SHAP analysis, a beeswarm plot, and LLM-based recommendation refinement.

4. **Explainability Technique**
   SHAP is used because it provides consistent feature attribution, supports both global and local explanations, and works well with Random Forest models.

5. **Dataset and Evaluation Metrics**
   The original study used rice-yield data from Tomioka-machi, Fukushima, Japan, covering 66 field-year records from 2021 to 2023.

6. **Experimental Results**
   The paper found that explanation quality follows an inverted U-shaped pattern: quality improves in early rounds, peaks around Rounds 3–4, and then declines when explanations become too complex.

7. **Design Principles**
   The presentation highlights the need for early stopping, hybrid human-LLM evaluation, observability protocols, and careful control of explanation complexity.

## Key Technical Understanding

The main technical idea is that SHAP provides the first layer of explanation, while the LLM provides a second layer that makes the explanation more human-readable and actionable.

The Agentic XAI process can be summarized as:

```text
Model prediction
        ↓
SHAP explanation
        ↓
LLM interpretation
        ↓
Gap identification
        ↓
Additional analysis
        ↓
Recommendation refinement
        ↓
Quality evaluation
```

## Important Findings from the Paper

The paper found that more explanation is not always better. Early rounds improve the explanation because they add useful context and evidence. However, later rounds can introduce too much detail, making the explanation longer, more complex, and less practical.

The best explanation quality was observed around **Rounds 3–4**. After that, over-refinement reduced clarity and usefulness.

## Materials Included

This folder includes:

```text
Task2_Presentation.pdf
```

The presentation contains the technical explanation of the selected paper, including motivation, methodology, system architecture, SHAP explanation, dataset details, evaluation metrics, experimental results, and key conclusions.

## Outcome of Task 2

The outcome of Task 2 was a technical presentation that demonstrated understanding of the selected paper and prepared the team for the reproduction phase in Task 3.

This task helped clarify:

* How Agentic XAI differs from traditional XAI.
* Why SHAP is used as the explainability method.
* How the LLM supports explanation refinement.
* Why optimal explanation depth is important.
* Why stopping criteria are needed in Agentic XAI systems.

## Conclusion

Task 2 provided the technical foundation for the rest of the project. By analyzing and presenting the selected paper, the team established a clear understanding of the Agentic XAI workflow, the role of SHAP and LLMs, and the paper’s main finding that explanation quality improves only up to an optimal point before declining due to over-refinement.
