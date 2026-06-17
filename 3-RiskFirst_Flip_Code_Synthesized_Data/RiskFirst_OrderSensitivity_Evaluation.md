# Risk-First Order-Sensitivity Evaluation

## Experiment

Executed sequence:

`0 -> 1 -> 2 -> 7 -> 8 -> 3 -> 4 -> 5 -> 6 -> 9 -> 10`

The dataset, Random Forest configuration, SHAP calculation, and analytical
round code were retained from the synthetic baseline.

## Execution Result

The first execution failed after the reordered Round 8 because that round used
the global variable name `y` for a plotting coordinate. This replaced the
target Series with an integer and caused original Round 3 to fail.

The experiment notebook was corrected by:

- preserving the trained-model state after Round 2;
- running original Rounds 7 and 8 early;
- restoring the preserved model state before original Round 3.

No analytical formulas or baseline files were changed. After state isolation,
the full risk-first sequence executed successfully and generated all ten PDFs.

## Comparison With Original Order

The core results did not change:

- 66 observations
- 37 predictors
- best model: 200-tree Random Forest
- leave-one-out cross-validation R2: 0.2215
- training R2: 0.8951
- training RMSE: 0.163 t/ha
- dominant feature: `Radiation4`
- `Radiation4` mean absolute SHAP value: 0.2372

The recommendation text embedded in the analytical code also remained
unchanged. Original Round 10 still concludes that:

- more than 90% of farmers should avoid optimization;
- only 8.5% have adequate resources;
- fewer than 2% are suitable for an intensive approach.

These values are hardcoded scenario assumptions rather than estimates from the
66-row synthetic dataset.

## Observed Numerical Difference

Original Round 9:

- confidence-interval width: 0.199 R2 units
- performance range: 0.103 to 0.302

Risk-first Round 9:

- confidence-interval width: 0.148 R2 units
- performance range: 0.146 to 0.294

This is not evidence that the risk-first sequence improved the model. Round 9
draws random values without initializing its own random seed. Moving Rounds 7
and 8 changes how many random values are consumed before Round 9, which changes
its simulated distribution.

The difference is therefore a random-state artifact, not an Agentic XAI
refinement effect.

## Recommendation-Quality Score

Because the final embedded Round 10 recommendation is unchanged, its
preliminary score remains:

| Endpoint | Score |
|---|---:|
| Stop at Round 4 | 28/35 |
| Original full baseline | 16/35 |
| Risk-first static-cell order | 16/35 |

## Interpretation

The risk-first experiment does not currently improve recommendation quality.
It demonstrates two important properties of the released workflow:

1. The notebook rounds are not independent modules. Temporary plotting
   variables can overwrite core model variables.
2. Reordering code cells is not equivalent to reordering an agentic refinement
   process. The notebook does not automatically regenerate an LLM
   recommendation after each round, so later text cannot react to information
   presented earlier.

This negative result is scientifically useful. It shows that order sensitivity
must be tested at the recommendation-generation level, not only at the
figure-generation level.

## Requirements for a Valid Agentic Order Test

For both the original and risk-first sequences:

1. Generate a recommendation after every round with the same LLM.
2. Feed each recommendation into the next reflection prompt.
3. Use identical prompts, model version, temperature, and seed settings.
4. Give each stochastic analytical round its own fixed random seed.
5. Repeat each complete sequence at least three times.
6. Score blinded outputs with multiple evaluators.

## Conclusion

The current risk-first run should be retained as a technical and methodological
finding, but not presented as evidence that risk-first ordering is better. The
available evidence shows that static reordering leaves the final recommendation
unchanged and introduces state-related execution and randomness artifacts.

