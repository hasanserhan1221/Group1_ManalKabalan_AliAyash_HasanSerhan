# Round 02 Recommendation Draft

## Analysis Module

error_and_subgroup_audit

## Controller Decision

The global metrics hide subgroup and location-dependent behavior. The worst observed subgroup is {'feature': 'Elevation', 'group': '(900.924, 1114.59]', 'count': 9778, 'error_rate': 0.6152587441194518}. The next round examines how influential features change predictions and whether apparent effects are conditional on other features.

## Evidence

```json
{
  "audited_source_features": [
    "Elevation_",
    "Elevation",
    "Aspect",
    "LUC_majori"
  ],
  "minimum_group_size": 195,
  "worst_subgroup": {
    "feature": "Elevation",
    "group": "(900.924, 1114.59]",
    "count": 9778,
    "error_rate": 0.6152587441194518
  },
  "reference_disagreement_counts": [
    {
      "status": "both_correct",
      "count": 21283
    },
    {
      "status": "reference_only_correct",
      "count": 15993
    },
    {
      "status": "new_model_only_correct",
      "count": 977
    },
    {
      "status": "both_wrong",
      "count": 891
    }
  ],
  "spatial_columns_used": [
    "X",
    "Y"
  ]
}
```

## LLM Self-Reflection

`LLM_PROVIDER` is set to `manual`. In manual mode, submit the generated
prompt to the same LLM configuration used for every round and replace this
section with its response.

## Proposed Next Analysis

feature_behavior_and_interactions
