# Round 01 Recommendation Draft

## Analysis Module

generalization_and_calibration

## Controller Decision

The balanced-accuracy train-test gap is 0.4155, classified as large. The next round must locate where errors concentrate rather than adding more global importance plots.

## Evidence

```json
{
  "train_test_metrics": [
    {
      "metric": "accuracy",
      "train": 0.9991916764926175,
      "test": 0.5686695278969958
    },
    {
      "metric": "balanced_accuracy",
      "train": 0.9991977923806283,
      "test": 0.5837437422808016
    },
    {
      "metric": "precision",
      "train": 0.9988363834192193,
      "test": 0.6721821756225426
    },
    {
      "metric": "recall",
      "train": 0.9995160900072586,
      "test": 0.3891312594840668
    },
    {
      "metric": "f1",
      "train": 0.9991761211177542,
      "test": 0.49291206150888994
    }
  ],
  "bootstrap_intervals": [
    {
      "metric": "accuracy",
      "mean": 0.5683416360106274,
      "ci_2_5": 0.5633813611281423,
      "ci_97_5": 0.5732245043940323
    },
    {
      "metric": "balanced_accuracy",
      "mean": 0.5833851782208221,
      "ci_2_5": 0.5787806425598343,
      "ci_97_5": 0.587395445513213
    },
    {
      "metric": "precision",
      "mean": 0.6715038173239627,
      "ci_2_5": 0.6631475514124778,
      "ci_97_5": 0.6794544815340514
    },
    {
      "metric": "recall",
      "mean": 0.3889804162862775,
      "ci_2_5": 0.3829038126844109,
      "ci_97_5": 0.3959288035424462
    },
    {
      "metric": "f1",
      "mean": 0.4926014288517848,
      "ci_2_5": 0.485877148972898,
      "ci_97_5": 0.4986835022155093
    },
    {
      "metric": "roc_auc",
      "mean": 0.6888496538758432,
      "ci_2_5": 0.6831643536815654,
      "ci_97_5": 0.6940912759465825
    }
  ],
  "generalization_gap": 0.4154540500998267,
  "calibration": {
    "brier_score": 0.23711826220948595,
    "expected_calibration_error": 0.14594532093949494
  }
}
```

## LLM Self-Reflection

`LLM_PROVIDER` is set to `manual`. In manual mode, submit the generated
prompt to the same LLM configuration used for every round and replace this
section with its response.

## Proposed Next Analysis

error_and_subgroup_audit
