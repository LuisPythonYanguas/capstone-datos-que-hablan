# CLAUDE.md — Capstone Option B: Data Analyst

## Project
**Datos que Hablan: Bienestar Financiero de Jóvenes Profesionales en América Latina**
(What the Data Says: Financial Wellness of Young Professionals in Latin America)

Junior data-analyst project for *Futuro Digital LatAm*. Goal: turn a raw survey CSV
(500 young professionals, 6 countries) into an executive analysis report that will
shape the organisation's next financial-literacy programme.

## Environment
- Python 3.12 in a local virtual environment at `venv/`
  - Run scripts with: `venv/Scripts/python.exe scripts/<name>.py` (Windows)
- Key libraries: **pandas**, **matplotlib**, **seaborn**, **scipy**

## Data
- Raw data: `data/latam_finanzas_2025.csv` (500 rows, 21 columns) — never modified
- Clean data: `data/latam_finanzas_clean.csv` — produced by Phase 2, used by all later phases

## Folder layout
- `scripts/` — all Python scripts, numbered by phase (`01_explore.py`, `02_clean.py`, ...)
- `charts/` — all PNG visualisations, numbered (`01_income_by_country.png`, ...)
- `.claude/agents/` — the `country-profiler` agent definition
- `analysis-report.md` — final executive report (repo root)

## Naming conventions
- Scripts: `NN_verb.py` (e.g. `01_explore.py`, `02_clean.py`, `03_analyse.py`, `04_visualise.py`)
- Per-country scripts: `scripts/country_<name>.py`
- Charts: `NN_description.png` (e.g. `01_income_by_country.png`)

## Chart standards
- Professional palette (not default matplotlib), clear title, labelled axes.
- Every chart carries the source note:
  *"Source: Encuesta de Bienestar Financiero LatAm 2025, Futuro Digital LatAm"*

## Report language
Report body is written in **English** (Spanish section titles per the spec).
