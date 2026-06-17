# Generalized Agentic XAI Refinement Summary

Domain context: wildfire occurrence classification using Earth observation, weather, terrain, and land-cover variables

## Completed Rounds

- Round 0: baseline model, SHAP explanation, diagnostics, and reference comparison.
- Round 1: generalization_and_calibration.
  Controller reason: The balanced-accuracy train-test gap is 0.4155, classified as large. The next round must locate where errors concentrate rather than adding more global importance plots.
- Round 2: error_and_subgroup_audit.
  Controller reason: The global metrics hide subgroup and location-dependent behavior. The worst observed subgroup is {'feature': 'Elevation', 'group': '(900.924, 1114.59]', 'count': 9778, 'error_rate': 0.6152587441194518}. The next round examines how influential features change predictions and whether apparent effects are conditional on other features.
- Round 3: feature_behavior_and_interactions.
  Controller reason: Global importance alone does not establish direction, thresholds, or conditional behavior. This round characterized binned SHAP effects and identified the strongest contribution co-movement pair as {'feature_1': 'Elevation__Low', 'feature_2': 'Elevation', 'spearman_shap_comovement': 0.42597443989775957}. The final round tests whether these explanations remain stable under permutation, perturbation, and SHAP resampling.
- Round 4: robustness_and_sensitivity.
  Controller reason: This final planned round tests whether the explanation survives held-out feature permutation, small input perturbations, and repeated SHAP resampling. Further refinement should occur only when the LLM reviewer identifies a specific unresolved contradiction supported by these files.

## Interpretation Rule

The workflow may stop after Round 4 unless the LLM self-reflection identifies a specific unresolved gap grounded in the generated evidence. Manual LLM mode creates prompts and recommendation drafts but does not invent an LLM response.

## Reproducibility Warning

Use the same dataset split, random seed, model parameters, LLM model, prompt settings, and human evaluation rubric when comparing recommendation rounds.