# Psychomotor development epidemiology analysis

Reproducible epidemiological analysis of factors associated with altered psychomotor development (DSM) in children aged 0–60 months using the 2019 and 2022 healthy-child-control datasets.

## Scope

This repository intentionally contains **only the epidemiological analysis**.

Primary outcome:
- `Normal` = 0
- `Riesgo` or `Retraso` = 1 (`Altered DSM`)

Main analyses:
1. Cohort characteristics by DSM status.
2. Multivariable logistic regression with HC3 robust standard errors.
3. Non-linear age adjustment using cubic B-splines.
4. Adjusted analysis of recorded vulnerability overall and by year.
5. Vulnerability × year interaction analysis.
6. Sensitivity analysis treating missing vulnerability status as an explicit category.

## Files

- `DSM_epidemiological_study_publication.ipynb` — main analysis notebook.
- `requirements.txt` — Python dependencies.

The source Excel dataset is **not included** in the repository due ethicals concerns.

## Default data path

For local execution, override paths with environment variables:

```bash
export DSM_PROJECT_DIR=/path/to/project
export DSM_DATA_PATH=/path/to/control_sano_2019_2022.xlsx
export DSM_OUTPUT_DIR=/path/to/output
```

## Reproducibility

The notebook prints and exports the Python and package versions used in each run. Statistical models use two-sided tests, HC3 robust standard errors, and clinically interpretable reference categories.

## Important interpretation note

The study is observational. Reported odds ratios represent **associations**, not causal effects. Vulnerability recording differs substantially between 2019 and 2022; this must be explicitly discussed as a limitation.
