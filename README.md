# Datos que Hablan — Bienestar Financiero de Jóvenes Profesionales en América Latina

Capstone Project · **Option B: Data Analyst** · Futuro Digital LatAm, 2025

Turning a raw survey of **500 young professionals** across six Latin American countries into an
executive analysis report to guide the region's next financial-literacy programme.

📄 **Read the full report:** [`analysis-report.md`](analysis-report.md)

---

## Key Findings

| # | Finding | Headline number |
|---|---|---|
| 1 | Income varies sharply by country | Brasil median $1,458 vs. Argentina $798 (**+83%**) |
| 2 | Savings rise with age | 5.7% (18–22) → 15.5% (29–32), **r = 0.41** |
| 3 | Essentials dominate budgets | Housing + food = **52%** of income |
| 4 | Cardholders spend more on discretionary items | +16% food, +17% entertainment at equal income |
| 5 | AI usage tracks satisfaction (confounded by income) | **r = 0.57**; high users earn 2.3× more |
| 6 | Housing burden is highest in the Southern Cone | Argentina **34%**, Chile **33%** of income |

---

## Repository Structure

```
capstone-option-b/
├── analysis-report.md              # Final executive report (deliverable 1)
├── CLAUDE.md                       # Project conventions for Claude Code
├── data/
│   ├── latam_finanzas_2025.csv     # Raw survey data (500 rows, 21 cols)
│   └── latam_finanzas_clean.csv    # Cleaned data (Phase 2 output)
├── scripts/                        # All analysis code (deliverable 2)
│   ├── 01_explore.py               # Phase 1 — exploration
│   ├── 02_clean.py                 # Phase 2 — cleaning
│   ├── _profile_lib.py             # Shared country-profile logic
│   ├── build_country_profiles.py   # Phase 2.5 — runs the agent for 6 countries
│   ├── country_<name>.py           # Per-country profile scripts (×6)
│   ├── country_profiles.md         # Collected country profiles
│   ├── 03_analyse.py               # Phase 3 — statistical analysis
│   ├── analysis_results.md         # Analysis tables (Phase 3 output)
│   └── 04_visualise.py             # Phase 4 — charts
├── charts/                         # 5 PNG visualisations (deliverable 3)
└── .claude/agents/
    └── country-profiler.md         # Custom agent definition (deliverable 4)
```

## How to Reproduce

```bash
python -m venv venv
venv\Scripts\activate                       # Windows (macOS/Linux: source venv/bin/activate)
pip install pandas matplotlib seaborn scipy tabulate

python scripts/01_explore.py                # Phase 1
python scripts/02_clean.py                  # Phase 2  -> data/latam_finanzas_clean.csv
python scripts/build_country_profiles.py    # Phase 2.5 -> scripts/country_profiles.md
python scripts/03_analyse.py                # Phase 3  -> scripts/analysis_results.md
python scripts/04_visualise.py              # Phase 4  -> charts/*.png
```

## The Six Phases

1. **Explore** — shape, dtypes, missing values, summary statistics.
2. **Clean** — standardise `industria`, median-fill `gasto_salud_usd`, flag negative savings.
3. **Country Profiler Agent** — one agent definition, six country profiles in parallel.
4. **Analyse** — six statistical analyses + two significant correlations.
5. **Visualise** — five professional charts.
6. **Interpret & Report** — plain-language findings and a leadership-ready executive report.


