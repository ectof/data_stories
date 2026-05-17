# Data Stories

A collection of data wrangling and analysis projects using Python and R, published with Quarto.

## Project structure

- `stories/` — Quarto documents (`.qmd`), one per story
- `src/` — reusable Python modules shared across stories
- `scripts/` — one-off Python data transformation scripts
- `R/` — reusable R functions
- `R/scripts/` — one-off R transformation scripts
- `data/raw/` — original source data, never modified (not tracked in git)
- `data/processed/` — cleaned/transformed outputs (not tracked in git)
- `data/external/` — third-party reference data (not tracked in git)
- `output/` — generated figures and reports (not tracked in git)

## Environment

- Python 3.13, managed with `uv`
- Activate venv: `source .venv/bin/activate`
- Install/sync deps: `uv sync`
- Add a package: add to `pyproject.toml` dependencies, then `uv sync`
- R dependencies managed with `renv` (run `renv::init()` in R to set up)
- Jupyter kernel: "Data Stories (3.13)"

## Running Quarto

```bash
quarto preview stories/<story>.qmd   # live preview
quarto render stories/<story>.qmd    # render to output/reports/
quarto render                        # render all stories
```

## Conventions

- Each story lives in its own `.qmd` file under `stories/`
- Reusable logic belongs in `src/` (Python) or `R/` (R), not in story files
- Raw data is never modified in place; write outputs to `data/processed/`
- Clear notebook outputs before committing
