# Round 03 Recommendation Draft

## Analysis Module

feature_behavior_and_interactions

## Controller Decision

Global importance alone does not establish direction, thresholds, or conditional behavior. This round characterized binned SHAP effects and identified the strongest contribution co-movement pair as {'feature_1': 'Elevation__Low', 'feature_2': 'Elevation', 'spearman_shap_comovement': 0.42597443989775957}. The final round tests whether these explanations remain stable under permutation, perturbation, and SHAP resampling.

## Evidence

```json
{
  "features_analyzed": [
    "Elevation__Low",
    "Elevation",
    "Aspect",
    "LUC_majori"
  ],
  "strongest_feature_effect": {
    "feature": "Elevation__Low",
    "spearman_value_shap": 0.8559643279364642,
    "mean_abs_shap": 0.06133357985780697
  },
  "strongest_comovement_pair": {
    "feature_1": "Elevation__Low",
    "feature_2": "Elevation",
    "spearman_shap_comovement": 0.42597443989775957
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
