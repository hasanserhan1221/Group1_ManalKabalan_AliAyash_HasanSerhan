# Round 04 Recommendation Draft

## Analysis Module

robustness_and_sensitivity

## Controller Decision

This final planned round tests whether the explanation survives held-out feature permutation, small input perturbations, and repeated SHAP resampling. Further refinement should occur only when the LLM reviewer identifies a specific unresolved contradiction supported by these files.

## Evidence

```json
{
  "held_out_sample_size": 2000,
  "baseline_held_out_score": 0.5837150986160003,
  "score_definition": "balanced_accuracy",
  "most_permutation_sensitive_feature": {
    "feature": "Elevation__Low",
    "baseline_score": 0.5837150986160003,
    "permuted_score_mean": 0.5435825255983668,
    "score_drop": 0.04013257301763351,
    "score_drop_std": 0.002243373358409295
  },
  "least_stable_reported_top_feature": {
    "feature": "B10",
    "mean_rank": 14.14,
    "rank_std": 0.7485986908885159,
    "top_10_frequency": 0.0
  }
}
```

## LLM Self-Reflection

`LLM_PROVIDER` is set to `manual`. In manual mode, submit the generated
prompt to the same LLM configuration used for every round and replace this
section with its response.

## Proposed Next Analysis

conditional_stop_or_targeted_follow_up
