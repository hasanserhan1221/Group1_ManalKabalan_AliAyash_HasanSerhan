# Round 04 Recommendation Draft

## Analysis Module

robustness_and_sensitivity

## Controller Decision

This final planned round tests whether the explanation survives held-out feature permutation, small input perturbations, and repeated SHAP resampling. Further refinement should occur only when the LLM reviewer identifies a specific unresolved contradiction supported by these files.

## Evidence

```json
{
  "held_out_sample_size": 2000,
  "baseline_held_out_score": 0.6058948610518747,
  "score_definition": "r2",
  "most_permutation_sensitive_feature": {
    "feature": "date_time_cos",
    "baseline_score": 0.6058948610518747,
    "permuted_score_mean": 0.16649066009764024,
    "score_drop": 0.4394042009542345,
    "score_drop_std": 0.014349394556726347
  },
  "least_stable_reported_top_feature": {
    "feature": "T6",
    "mean_rank": 16.17,
    "rank_std": 1.1666619047521862,
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
