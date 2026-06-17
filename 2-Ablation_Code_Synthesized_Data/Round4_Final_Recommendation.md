# Stop-at-Round-4 Final Recommendation

## Experiment Context

This recommendation uses only evidence available through original Round 4 of
the synthetic-data workflow. Later rounds and their economic, farmer-resource,
success-rate, and global-applicability assumptions are intentionally excluded.

Dataset and model evidence:

- 66 synthetic field records and 37 predictors
- Random Forest regression
- Leave-one-out cross-validation R2: 0.2215
- Training R2: 0.8951
- Training RMSE: 0.1630 t/ha
- Dominant feature: `Radiation4`
- `Radiation4` mean absolute SHAP value: 0.2372
- `Radiation4` correlation with yield: 0.6415

The large difference between training and cross-validation performance
indicates overfitting. SHAP results should therefore be interpreted as
hypotheses within this synthetic dataset, not as causal agronomic rules.

## Agronomic Insights

1. Late-stage solar radiation is the strongest model signal.

   `Radiation4` contributes substantially more to the model than any other
   feature. This supports investigating whether radiation conditions during the
   corresponding growth period are associated with yield differences.

2. Temperature, phosphorus, precipitation, and soil properties are secondary
   signals.

   Available phosphorus, early and later temperatures, early precipitation,
   carbon-nitrogen ratio, and organic matter appear among the next-ranked
   variables. Their SHAP contributions are much smaller than `Radiation4`, so
   the current data do not justify strong individual prescriptions.

3. The model is not sufficiently reliable for direct farm-wide optimization.

   Cross-validated performance is weak even though training performance is
   high. Recommendations should be tested locally before adoption, and the
   model should not be used to promise a specific yield increase.

4. The analysis identifies priorities for further measurement rather than
   universal thresholds.

   Values such as a 15% or 25% yield increase, a fixed temperature threshold,
   a universal soil-organic-matter range, or a fixed variety duration were not
   estimated or validated by this synthetic dataset.

## Specific Recommendations

1. Run a small controlled pilot before changing management across all fields.

   Compare current practice with a treatment designed to improve crop timing
   relative to the locally observed high-radiation period. Use several fields
   or plots and retain an untreated comparison group.

2. Record growth-stage timing and radiation consistently.

   Record transplanting, heading, grain-filling dates, radiation, temperature,
   precipitation, and final yield. This will test whether the `Radiation4`
   relationship persists in real field data.

3. Treat soil and nutrient variables as monitoring priorities.

   Measure available phosphorus, organic matter, and carbon-nitrogen ratio
   before recommending additional inputs. Use local agronomic guidance and soil
   tests rather than thresholds inferred from this model.

4. Prefer low-cost, reversible actions during validation.

   Prioritize monitoring, planting-date trials, and locally suitable variety
   comparisons. Avoid expensive changes until yield benefits and costs have
   been observed over more than one season.

5. Evaluate both agronomic and economic outcomes.

   For every pilot, record yield, input quantities, labor, intervention costs,
   and rice price. The current workflow does not contain validated local cost
   data, so it cannot establish profitability.

6. Improve the model before operational use.

   Add real observations from more fields, years, weather conditions, and
   management systems. Validate with field- or year-based holdouts to reduce
   leakage and test transferability.

## Final Decision

Proceed with a limited validation study focused on late-stage radiation and
growth-stage timing. Do not claim a guaranteed yield increase, prescribe
universal thresholds, or recommend expensive optimization from the current
synthetic model.

