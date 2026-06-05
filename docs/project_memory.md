# Project Memory

## Project

Repository: `ice-video-game-success-analysis`

This project analyzes historical video game sales for ICE, an online video game retailer. The analysis supports advertising planning for 2017 using data available through 2016.

The work should be framed as exploratory business analysis and historical planning guidance, not as a deterministic sales forecast.

## Business Goal

Identify commercially relevant patterns that can help ICE prioritize advertising decisions, including:

- Platforms with recent activity and meaningful sales potential.
- Genres with strong total sales or strong per-title performance.
- Regional differences in platform and genre preferences.
- Whether critic scores, user scores, and ESRB ratings provide useful context for sales decisions.

## Dataset

Expected source file:

```text
data/games.csv
```

The dataset may be absent from the repository. If reproducing the analysis, place the source dataset at that path.

Core fields used in the analysis include:

- `Name`
- `Platform`
- `Year_of_Release`
- `Genre`
- `NA_sales`
- `EU_sales`
- `JP_sales`
- `Other_sales`
- `Critic_Score`
- `User_Score`
- `Rating`

Sales values are treated as millions of units.

## Analysis Workflow

The notebook follows a standard exploratory data analysis flow:

- Inspect dataset structure and missing values.
- Clean data types and normalize column names where needed.
- Handle special score values such as `tbd`.
- Create total global sales from regional sales columns.
- Review platform sales history and platform lifecycle patterns.
- Focus on recent years that are more relevant to 2017 planning.
- Compare sales by platform and genre.
- Compare regional preferences across North America, Europe, Japan, and other regions.
- Examine score-sales relationships.
- Review ESRB rating patterns.
- Run statistical tests for selected user-score comparisons.

## Key Findings

- Sales are historically concentrated in leading platform families, especially PlayStation, Xbox, Wii, and DS.
- Platform lifecycles are limited, so advertising plans should account for recency and platform momentum.
- Action, Sports, and Role-Playing tend to show strong accumulated sales volume.
- Platform and Shooter genres tend to show stronger sales per title.
- Regional markets differ meaningfully; Japan often behaves differently from North America and Europe.
- Critic scores, user scores, and ESRB ratings are useful supporting context, but they should not be treated as primary sales predictors on their own.

## Limitations

- The data only includes releases through 2016.
- The project identifies associations and market patterns, not causal effects.
- Missing score and rating values are important data-quality caveats.
- Ratings and review scores capture only part of a game's commercial context.
- Conclusions should be used as planning guidance for 2017 rather than as a production forecasting model.

## Repository Structure

```text
ice-video-game-success-analysis/
├── data/
├── docs/
│   ├── data_dictionary.md
│   └── project_memory.md
├── notebooks/
│   └── ice_video_game_success_analysis.ipynb
├── reports/
│   └── figures/
├── README.md
├── requirements.txt
└── .gitignore
```

## Reproduction Notes

Install dependencies from:

```bash
pip install -r requirements.txt
```

Then open and run:

```bash
jupyter notebook notebooks/ice_video_game_success_analysis.ipynb
```

## Working Guidelines

- Do not modify the notebook unless explicitly requested.
- Keep documentation consistent with the existing README and notebook conclusions.
- Avoid overstating predictive claims.
- Keep dataset paths stable so the notebook remains reproducible.
- Store generated visual outputs under `reports/figures/`.
