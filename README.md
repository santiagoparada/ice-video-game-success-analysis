# Video Game Market Analysis for Advertising Strategy

Exploratory data analysis project for ICE, an online video game retailer. The notebook studies historical video game sales through 2016 to identify platform, genre, regional, score, and ESRB rating patterns that can inform advertising planning for 2017.

The analysis is descriptive and decision-support oriented. It should be read as historical market guidance, not as a deterministic forecasting model.

## Business Objective

The project answers practical planning questions:

- Which platforms show meaningful recent commercial potential?
- Which genres generate the strongest total sales and per-title sales?
- How do regional preferences differ across North America, Europe, Japan, and other regions?
- How useful are critic scores, user scores, and ESRB ratings as supporting sales signals?

## Dataset

Expected source file:

```text
data/games.csv
```

Core fields include game name, platform, release year, genre, regional sales, critic score, user score, and ESRB rating. Sales values are analyzed in millions of units.

The notebook creates:

```python
games["total_sales"] = games[["na_sales", "eu_sales", "jp_sales", "other_sales"]].sum(axis=1)
```

## Repository Structure

```text
ice-video-game-success-analysis/
├── data/
│   └── games.csv
├── docs/
│   ├── data_dictionary.md
│   └── project_memory.md
├── notebooks/
│   ├── ice_video_game_success_analysis.ipynb
│   └── ice_video_game_success_analysis_backup_before_fix_cell49.ipynb
├── reports/
│   ├── execution_report.md
│   └── figures/
├── requirements.txt
└── README.md
```

## Methodology

The notebook follows a standard EDA workflow:

- Load and clean the dataset.
- Normalize text values and convert score columns.
- Create total global sales from regional sales.
- Analyze platform lifecycle and platform sales concentration.
- Compare sales by decade, platform, genre, and region.
- Review critic-score and user-score relationships with sales.
- Compare user-score distributions with statistical tests.
- Review ESRB rating patterns across regions.

## Skills Demonstrated

- Exploratory Data Analysis (EDA)
- Data Cleaning and Validation
- Feature Engineering
- Statistical Hypothesis Testing
- Correlation Analysis
- Business-Oriented Data Analysis
- Data Visualization
- pandas
- NumPy
- Seaborn
- SciPy
- Jupyter Notebook

## Key Findings

- Sales are historically concentrated in major platform families such as PlayStation, Xbox, Wii, DS, and PC.
- Platform lifecycles are limited, so advertising timing matters.
- Action, Sports, and Role-Playing show strong accumulated sales volume.
- Platform and Shooter genres show stronger per-title performance.
- Regional demand patterns differ meaningfully, especially between Japan and Western markets.
- Critic scores, user scores, and ESRB ratings are useful context, but they should not be treated as standalone sales predictors.

## Statistical Analysis

The project includes:

- Correlation analysis between review scores and sales.
- Welch's t-test comparing Xbox One and PC user scores.
- Welch's t-test comparing Action and Sports user scores.
- Business interpretation of statistical significance and market relevance.

## Reproducibility

Create and activate a Python environment, then install dependencies:

```bash
pip install -r requirements.txt
```

Run the notebook:

```bash
jupyter notebook notebooks/ice_video_game_success_analysis.ipynb
```

The notebook uses a relative dataset path:

```python
DATA_PATH = Path("../data/games.csv")
```

Run it from the `notebooks/` directory or through Jupyter with the notebook as the active working context.

## Validation Status

The notebook has been executed successfully from top to bottom.

Latest execution metrics:

- `games.shape`: `(16715, 12)`
- `games["total_sales"].count()`: `16715`
- Rendered image outputs: `20`
- Saved notebook error outputs: `0`

See [reports/execution_report.md](reports/execution_report.md) for the final execution and audit report.

## Technologies

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook
- Git
- GitHub
