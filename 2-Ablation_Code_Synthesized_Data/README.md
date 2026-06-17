# Stop-at-Round-4 Ablation

Sequence: `0 -> 1 -> 2 -> 3 -> 4`

Purpose: test whether later refinement rounds improve recommendation quality
or introduce over-refinement.

## Run protocol

1. Start a fresh kernel.
2. Open `PythonCode_StopAt4_Ablation.ipynb` from this folder.
3. Run all cells in order.
4. Regenerate the LLM recommendation after every round.
5. Treat the recommendation after Round 4 as the final ablation output.
6. Compare it with the original baseline using the paper's seven criteria.

The CSV is copied locally so this experiment does not read or write the
baseline folder.

## Environment and file locations

Run the first code cell before Round 0. It installs any missing Python
libraries into the selected kernel. The notebook reads
`agriculture_data_v2.csv` from this folder and writes all generated PDFs to
this same folder.
