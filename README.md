# Generative AI and Early-Career Labour Demand in Sweden

**Master's thesis analysis | Information Systems | Uppsala University (2026)**

This repository presents selected Python analysis and visualisations from *Disappearing Junior Jobs? Generative AI and Early-Career Labour Demand in Sweden*. The project examines how occupation-level exposure to generative AI is associated with Swedish early-career job-advertisement patterns from **2021 to 2025**.

## Research questions
1. Which Swedish occupations have the highest generative-AI exposure based on job-advertisement text?
2. How has early-career job-advertisement demand changed across occupational AI-exposure groups?

## Scope and approach
- Source: Swedish Public Employment Service (Arbetsförmedlingen) job-advertisement data.
- Original data loaded in the notebook: **3,641,098 rows**; 3,638,560 after year filtering; **3,613,228 retained postings**, in **1,938 occupations**, after the minimum-50-postings occupation rule.
- Text-based early-career keywords applied to titles and descriptions.
- Keyword-based posting AI-exposure score aggregated by occupation and ranked into five equally sized occupation groups.
- Year-by-group comparisons, statistical tests, OLS models, and charts.

## Selected results from saved notebook outputs
| AI-exposure quintile | Early-career postings, 2021 | Early-career postings, 2025 | Change |
|---|---:|---:|---:|
| Very Low | 28,993 | 26,146 | -9.8% |
| Low | 35,584 | 36,322 | +2.1% |
| Medium | 30,621 | 26,669 | -12.9% |
| High | 52,104 | 40,622 | -22.0% |
| Very High | 48,205 | 37,961 | -21.3% |

These figures come from the **uploaded notebook's saved outputs**, and may differ from earlier thesis drafts. They show **descriptive associations, not evidence that AI caused the change**.

## Visualisations
![Growth decomposition comparing early-career share changes, early-career posting volumes, and total demand]
<img width="2380" height="854" alt="image" src="https://github.com/user-attachments/assets/f72d3048-78e2-4a37-abe6-6a8015f810cb" />

## Repository contents
- `notebooks/chapter4_analysis.ipynb` — original analysis, documented and with two small operational/display fixes
- `figures/` — charts extracted from existing notebook outputs (not recalculated)
- `requirements.txt` — Python dependencies
- `.gitignore` — common Python files and local large-data paths ignored

## How to run
1. Install Python and Jupyter; set up a virtual environment if desired.
2. Run `pip install -r requirements.txt`.
3. Place an **authorised copy** of `jobs_2021_2025.csv` in the notebook working directory (`notebooks/` when opened there), or change `file_path` to its local location.
4. Run cells in order. The notebook writes result tables and figure files to its working directory.

**The original dataset is intentionally excluded.** Without it, the full analysis cannot be rerun directly from this repository.

## Limitations and checks
- Job ads measure advertised vacancies, not realised hires or employment.
- Early-career status and AI exposure are constructed using imperfect keyword heuristics.
- Some matching is based on substrings; the string `ai` can match in unrelated words.
- The negative-context score cap **does not fully achieve its stated objective**: the notebook's saved audit still puts several named false-positive occupations in the *High* group.
- The notebook's Model 2 describes a continuous quintile interaction, but its output shows categorical quintile terms. `post2022` also overlaps with year fixed effects; model specification should be reviewed.
- These issues are **documented, not silently repaired**, to avoid changing reported research results without rerunning and validating the full analysis.
- The figures are extracted from the notebook's existing cached outputs and have not been recomputed.

## Technologies
Python, pandas, NumPy, Matplotlib, SciPy, statsmodels, Jupyter Notebook.

## Author
Sabira Ataee — MSc Information Systems, Uppsala University.
