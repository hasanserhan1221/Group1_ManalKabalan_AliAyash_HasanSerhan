# Generalized Agentic XAI Refinement Summary

Domain context: appliance energy consumption prediction using indoor temperature and humidity measurements, outdoor weather conditions, lighting, and time context

## Completed Rounds

- Round 0: baseline model, SHAP explanation, diagnostics, and reference comparison.
- Round 1: generalization_and_split_sensitivity.
  Controller reason: The conventional random test R2 is 0.6171, but grouped-date R2 is -0.0527 and future-period R2 is -3.6599. This large split sensitivity indicates that neighboring observations and temporal distribution shift materially affect the apparent model quality. The next round must locate where errors concentrate.
- Round 2: error_and_subgroup_audit.
  Controller reason: The global metrics hide subgroup-dependent behavior. The worst observed subgroup is {'feature': 'lights', 'group': '30', 'count': 104, 'mae': 50.42532051282051}. The next round examines how influential features change predictions and whether apparent effects are conditional on other features.
- Round 3: feature_behavior_and_interactions.
  Controller reason: Global importance alone does not establish direction, thresholds, or conditional behavior. This round characterized binned SHAP effects and identified the strongest contribution co-movement pair as {'feature_1': 'date_time_sin', 'feature_2': 'date_time_cos', 'spearman_shap_comovement': 0.4315161715161715}. The final round tests whether these explanations remain stable under permutation, perturbation, and SHAP resampling.
- Round 4: robustness_and_sensitivity.
  Controller reason: This final planned round tests whether the explanation survives held-out feature permutation, small input perturbations, and repeated SHAP resampling. Further refinement should occur only when the LLM reviewer identifies a specific unresolved contradiction supported by these files.

## Interpretation Rule

The workflow may stop after Round 4 unless the LLM self-reflection identifies a specific unresolved gap grounded in the generated evidence. Manual LLM mode creates prompts and recommendation drafts but does not invent an LLM response.

## Reproducibility Warning

Use the same dataset split, random seed, model parameters, LLM model, prompt settings, and human evaluation rubric when comparing recommendation rounds.