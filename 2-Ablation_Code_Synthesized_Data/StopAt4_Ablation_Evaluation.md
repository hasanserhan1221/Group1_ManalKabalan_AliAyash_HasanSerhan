# Stop-at-Round-4 Ablation Evaluation

## Objective

This assessment tests whether ending the workflow after original Round 4
produces a more defensible recommendation than continuing to the existing
synthetic baseline endpoint at original Round 10.

The analytical figures from Rounds 1-4 are expected to match the corresponding
baseline figures because the dataset and code are unchanged. The ablation tests
the quality of the recommendation endpoint, not prediction improvement.

## Compared Endpoints

### Stop-at-Round-4 endpoint

The Round 4 endpoint was regenerated using only evidence available through
Round 4. Claims not estimated by the data were removed or explicitly marked as
unvalidated hypotheses.

### Existing full-baseline endpoint

The baseline endpoint is the recommendation text embedded in original Round 10
of the synthetic Task 3 notebook. It contains strong claims including:

- 47% probability of financial loss
- only 8.5% of farmers having adequate resources
- more than 90% of farmers being advised to avoid optimization
- optimization being suitable for fewer than 2% of farmers globally
- fixed income, capital, price, and success-rate thresholds

These values come from hardcoded assumptions and simulated distributions in the
notebook. They were not estimated from the 66-row synthetic rice dataset or
from observed farmer-resource data.

## Scoring Rubric

Each paper criterion is scored from 1 to 5:

- 1: very weak
- 2: weak
- 3: acceptable
- 4: strong
- 5: very strong

| Criterion | Stop at Round 4 | Full baseline Round 10 | Main reason |
|---|---:|---:|---|
| Clarity | 5 | 3 | Round 4 separates evidence, uncertainty, and actions. |
| Conciseness | 4 | 2 | Round 10 contains many stakeholder claims and repeated warnings. |
| Specificity | 4 | 4 | Both provide concrete actions, but some Round 10 precision is unsupported. |
| Practicality | 4 | 2 | A limited pilot is executable; broad exclusion of most farmers is not locally validated. |
| Contextual relevance | 4 | 1 | Round 4 remains tied to this dataset; Round 10 makes global farmer claims without local data. |
| Cost consideration | 3 | 3 | Round 4 requests real cost tracking; Round 10 discusses costs using assumed values. |
| Crop-science credibility | 4 | 1 | Round 4 uses cautious agronomic hypotheses; Round 10 overgeneralizes simulated assumptions. |
| **Total** | **28/35** | **16/35** | The early endpoint is more evidence-disciplined. |

Additional diagnostic:

| Diagnostic | Stop at Round 4 | Full baseline Round 10 |
|---|---:|---:|
| Evidence groundedness | 5/5 | 1/5 |

## Interpretation

The stop-at-Round-4 ablation adds value in this implementation because it
prevents later hardcoded scenario assumptions from being presented as measured
facts. It produces a shorter, more locally relevant, and more scientifically
cautious recommendation.

It does not prove that later refinement is inherently harmful. Later rounds
could improve recommendations if they used validated cost, farmer-resource,
market, uncertainty, and external agronomic data. The observed decline is
caused largely by the quality and provenance of the added evidence, not simply
by the number of rounds.

## Remaining Experimental Limitations

This is a preliminary artifact-based evaluation, not a statistically controlled
LLM study:

- The original sequential LLM outputs for the synthetic baseline were not
  saved.
- The Round 4 endpoint and embedded Round 10 text were not generated in the
  same run with an identical LLM configuration.
- The scores were assigned by one evaluator.
- No repeated LLM runs or inter-rater agreement are available.

For a defensible final course result, regenerate both endpoints with the same
LLM, prompt, temperature, and evidence format, repeat each condition at least
three times, and use two or more blinded evaluators.

## Conclusion

The current evidence supports retaining the stop-at-Round-4 experiment. Its
main contribution is demonstrating that additional refinement can reduce
recommendation reliability when new rounds introduce unvalidated assumptions.
The result should be described as preliminary evidence of over-refinement, not
proof that Round 4 is universally optimal.

