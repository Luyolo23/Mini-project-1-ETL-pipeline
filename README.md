# Mini-project 1 — Simple ETL pipeline (Users data)

Short description
-----------------
This repository contains a minimal ETL (Extract-Transform-Load) pipeline implemented inside a Jupyter notebook. The pipeline reads user data from `data/users.csv`, performs basic cleaning and transformations, and writes the cleaned output to `cleaned_data.csv`.

What’s included
----------------
- `etl_pipeline.ipynb` — the notebook implementing extract, transform, and load steps.
- `data/users.csv` — sample input data (source).
- `cleaned_data.csv` — pipeline output (written after running the notebook).

High-level contract
-------------------
- Input: `data/users.csv` (CSV with columns such as `email`, `age`, `city`, ...).
- Output: `cleaned_data.csv` (cleaned, transformed CSV).
- Errors: The pipeline drops rows with missing `age` values and converts `age` to integer; rows with other missing non-critical fields get sensible defaults.

Quick start
-----------
1. Install required packages (recommended inside a virtualenv):

```bash
python -m pip install --upgrade pip
python -m pip install pandas jupyter
```

2. Run interactively

- Open the notebook in Jupyter and run the cells in order. Example:

```bash
jupyter notebook etl_pipeline.ipynb
```

3. Run headless (execute the notebook end-to-end)

- To execute the notebook and write `cleaned_data.csv` without opening the browser, use:

```bash
jupyter nbconvert --execute --inplace etl_pipeline.ipynb
```

Notes
-----
- The notebook defines three functions: `extract()` (reads `data/users.csv`), `transform(df)` (cleans/augments data), and `load(df)` (writes `cleaned_data.csv`).
- The pipeline currently drops rows where `age` is missing and converts `age` to `int`.
- The notebook creates `email_provider` and `name` by parsing the `email` field and fills missing `city` values with `Unknown`.

