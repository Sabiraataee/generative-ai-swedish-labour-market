# Review notes: supplied thesis notebook

The notebook was **not executed**, because `jobs_2021_2025.csv` was not supplied.

## Packaging changes made
1. Added a portfolio transparency note near the beginning of the notebook.
2. Changed CSV loading to read a CSV directly and provide a clear error when the source file is missing. Previously the notebook tried the Excel engine first.
3. Changed Figure 4.3 y-axis from `20–75` to `0–60`, because the recorded values for Very Low and Low exposure groups are around 12–25% and would otherwise be hidden. Saved figure is still the **original**, unrecomputed one.
4. Extracted existing in-notebook PNG figure outputs; did not manufacture analysis results.
5. Added a README and dependency list and a `.gitignore` to help avoid publishing large raw datasets.

## Issues left unchanged because they alter analytical conclusions
- **False-positive correction fails its stated guarantee.** Saved output still categorises `barntimmeledare` and `anonym konsument` (among others) as **High**. Merely capping scores at the approximate 60th percentile does not guarantee a rank below the High boundary after ties and reranking. Some occupation patterns are corrected twice due to overlapping matching terms. Fix and rerun the full pipeline before treating it as resolved.
- **Substring keyword matching.** `ai` and `entry`, among others, can match parts of unrelated words. A language-aware or word-boundary matching strategy could differ from the thesis results and needs testing.
- **Regression model label inconsistent with output.** `q_numeric` remains categorical in the saved output (terms such as `q_numeric[T.2]`), rather than the stated continuous slope. `post2022` is redundant with full year fixed effects. Re-specify with a clear estimand and evaluate the assumptions.
- **Potentially stale outputs.** Old saved figures and printed tables should be regenerated after any methodological updates. No raw data was supplied to verify outputs.
- A large unqualified statement that low exposure/high exposure occupations were incorrectly classified is not justified by this notebook alone; validity requires further checks.
