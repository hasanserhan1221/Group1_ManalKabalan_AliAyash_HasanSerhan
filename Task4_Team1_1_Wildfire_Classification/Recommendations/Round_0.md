# Round 00 Recommendations

LLM_PROVIDER is set to manual.

Use the generated prompt, then replace this placeholder with the LLM response.

## Evidence Snapshot

Domain context: wildfire occurrence classification using Earth observation, weather, terrain, and land-cover variables

Task type: classification

New-model metrics:
{
  "train_accuracy": 0.9991916764926175,
  "train_balanced_accuracy": 0.9991977923806283,
  "train_precision": 0.9988363834192193,
  "train_recall": 0.9995160900072586,
  "train_f1": 0.9991761211177542,
  "test_accuracy": 0.5686695278969958,
  "test_balanced_accuracy": 0.5837437422808016,
  "test_precision": 0.6721821756225426,
  "test_recall": 0.3891312594840668,
  "test_f1": 0.49291206150888994,
  "test_roc_auc": 0.6892282854895713
}

Reference-model metrics:
{
  "accuracy": 0.9522787655834866,
  "balanced_accuracy": 0.9510232307950379,
  "precision": 0.9454435895058867,
  "recall": 0.9672325493171472,
  "f1": 0.9562139609019736,
  "roc_auc": 0.9834381437567694
}

Top SHAP features:
          feature  mean_abs_shap
   Elevation__Low       0.061334
        Elevation       0.059442
           Aspect       0.040211
       LUC_majori       0.036837
            Slope       0.036061
  Elevation__High       0.033137
           B4_num       0.026491
             NDVI       0.021542
           B5_num       0.020172
Elevation__Medium       0.017884
           B3_num       0.015370
          B11_num       0.015090
             NDWI       0.013282
              B10       0.012698
           B1_num       0.012499
           B2_num       0.011427
           B6_num       0.009379
              NBR       0.008559
         wind_spd       0.008223
          B12_num       0.007615
