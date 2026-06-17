# Risk-First Order-Sensitivity Experiment

Sequence: `0 -> 1 -> 2 -> 7 -> 8 -> 3 -> 4 -> 5 -> 6 -> 9 -> 10`

Purpose: test whether introducing validation, reliability, uncertainty, and
failure analysis earlier changes the later recommendation trajectory.

## Run protocol

1. Start a fresh kernel.
2. Open `PythonCode_RiskFirst_OrderSensitivity.ipynb` from this folder.
3. Run all cells in the displayed order.
4. Regenerate the LLM recommendation after every round.
5. Pass each recommendation into the next reflection step.
6. Compare the final recommendation with the original baseline and the
   stop-at-Round-4 ablation using the same rubric.

Original Round 8 received one dependency fix: it now imports
`matplotlib.gridspec` directly because it executes before original Round 3.
No baseline files are modified.

## Environment and file locations

Run the first code cell before Round 0. It installs any missing Python
libraries into the selected kernel. The notebook reads
`agriculture_data_v2.csv` from this folder and writes all generated PDFs to
this same folder.
