# Round 00 Recommendations

LLM_PROVIDER is set to manual.

Use the generated prompt, then replace this placeholder with the LLM response.

## Evidence Snapshot

Domain context: appliance energy consumption prediction using indoor temperature and humidity measurements, outdoor weather conditions, lighting, and time context

Task type: regression

New-model metrics:
{
  "train_r2": 0.9460713193809067,
  "train_rmse": 23.950126341699153,
  "train_mae": 11.23995017312727,
  "train_mape": 0.10969521434629088,
  "test_r2": 0.6170616627346055,
  "test_rmse": 61.903948375072275,
  "test_mae": 29.167789882611267,
  "test_mape": 0.29333951677971043
}

Reference-model metrics:
null

Top SHAP features:
      feature  mean_abs_shap
date_time_sin      24.170251
date_time_cos      21.524943
       lights       7.642585
date_week_sin       6.857177
  Press_mm_hg       4.591877
           T3       4.543890
         RH_3       3.807690
           T8       3.367678
           T5       3.292538
         RH_1       3.033839
           T2       2.946845
         RH_5       2.757446
date_week_cos       2.740305
    Tdewpoint       2.590907
           T6       2.311441
    Windspeed       2.298564
         RH_4       2.216257
         RH_8       2.214251
         RH_2       2.058071
        T_out       2.006004
