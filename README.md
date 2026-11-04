# Psychomotor development epidemiology analysis

Reproducible epidemiological analysis of factors associated with altered psychomotor development (DSM) in children aged 0–60 months using the 2019 and 2022 healthy-child-control datasets.

## Scope

This repository intentionally contains **only the epidemiological analysis**. Exploratory machine-learning experiments were removed from the cleaned notebook.

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

The source Excel dataset is **not included** in the repository.

## Default data path

The notebook preserves the original Google Drive project structure:

```text
/content/drive/MyDrive/Machine_Learning_UCT/psicomotor/control_sano_2019_2022.xlsx
```

The publication outputs are written by default to:

```text
/content/drive/MyDrive/Machine_Learning_UCT/psicomotor/final_estudiantes/epidemiology_publication/
```

For local execution, override paths with environment variables:

```bash
export DSM_PROJECT_DIR=/path/to/project
export DSM_DATA_PATH=/path/to/control_sano_2019_2022.xlsx
export DSM_OUTPUT_DIR=/path/to/output
```

## Outputs

Tables are exported as both CSV and XLSX. Figures are exported as PNG and TIFF at **300 dpi**.

Main publication outputs include:

- Table 1: cohort characteristics by DSM status.
- Table 2: adjusted odds ratios from the core model.
- Table 3: altered DSM prevalence by recorded vulnerability.
- Table 4: adjusted vulnerability association overall and by year.
- Table 5: vulnerability × year interaction.
- Figure 1: core adjusted-OR forest plot.
- Figure 2: altered DSM prevalence by vulnerability.
- Figure 3: adjusted vulnerability-OR forest plot.

Supplementary outputs include the cohort flow, missingness audit, global Wald tests, vulnerability missing-status sensitivity analysis, model summaries, software versions, and a JSON analysis manifest.

## Reproducibility

The notebook prints and exports the Python and package versions used in each run. Statistical models use two-sided tests, HC3 robust standard errors, and clinically interpretable reference categories.

## Important interpretation note

The study is observational. Reported odds ratios represent **associations**, not causal effects. Vulnerability recording differs substantially between 2019 and 2022; this must be explicitly discussed as a limitation.
