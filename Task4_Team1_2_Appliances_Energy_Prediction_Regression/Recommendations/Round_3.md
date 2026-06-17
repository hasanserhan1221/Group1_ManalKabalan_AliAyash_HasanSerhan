# Round 03 Recommendation Draft

## Analysis Module

feature_behavior_and_interactions

## Controller Decision

Global importance alone does not establish direction, thresholds, or conditional behavior. This round characterized binned SHAP effects and identified the strongest contribution co-movement pair as {'feature_1': 'date_time_sin', 'feature_2': 'date_time_cos', 'spearman_shap_comovement': 0.4315161715161715}. The final round tests whether these explanations remain stable under permutation, perturbation, and SHAP resampling.

## Evidence

```json
{
  "features_analyzed": [
    "date_time_sin",
    "date_time_cos",
    "lights",
    "date_week_sin"
  ],
  "strongest_feature_effect": {
    "feature": "date_time_sin",
    "spearman_value_shap": -0.8056494997823073,
    "mean_abs_shap": 24.170250691929414
  },
  "strongest_comovement_pair": {
    "feature_1": "date_time_sin",
    "feature_2": "date_time_cos",
    "spearman_shap_comovement": 0.4315161715161715
  },
  "interaction_warning": "Contribution co-movement is a screening proxy and must not be reported as a causal or formal interaction estimate."
}
```

## LLM Self-Reflection

`LLM_PROVIDER` is set to `manual`. In manual mode, submit the generated
prompt to the same LLM configuration used for every round and replace this
section with its response.

## Proposed Next Analysis

robustness_and_sensitivity
