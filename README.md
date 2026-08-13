# Spotify Song Popularity — EDA & Predictive Modeling

A two-phase project examining which track and playlist features relate to
song popularity, using the Spotify Songs dataset from
[TidyTuesday](https://github.com/rfordatascience/tidytuesday) (~32,833 tracks).
Completed as a course-long project for an M.S. in Data Science program.

## Dataset

- Source: TidyTuesday Spotify Songs dataset
- ~32,833 tracks
- Outcome variable: `track_popularity`, logit-transformed for regression modeling

## Phase 1: Exploratory Data Analysis

- Data loading and cleaning with Pandas and NumPy
- Focused the analysis on 8 variables:
  - Categorical: `playlist_genre`, `playlist_subgenre`
  - Continuous: `danceability`, `energy`, `loudness`, `instrumentalness`,
    `valence`, `tempo`
- Visualizations built with Matplotlib and Seaborn: bar charts, histograms /
  KDE plots, faceted violin plots, scatter plots with regression lines, and a
  correlation heatmap
- Key finding: playlist genre and subgenre influenced popularity more than
  any single continuous audio feature

## Phase 2: Predictive Modeling

- Built and compared 6 linear regression models of increasing complexity,
  from an intercept-only baseline through models with pair-wise interactions
  and quadratic transformations
- Standardized continuous inputs and evaluated each model's coefficients,
  statistical significance, R-squared, and RMSE
- Model 6 (56 coefficients) had the best training performance
  (R-squared = 0.116, RMSE = 2.080), but 10-fold cross-validation showed
  Model 4 (35 coefficients, all inputs, no interactions/quadratics)
  generalized comparably — so Model 4 was selected as the better model for
  its lower complexity
- Most influential predictors: `playlist_subgenre`, `energy` (negative
  effect on popularity), and `loudness` (positive effect) — consistent with
  and extending the Phase 1 EDA findings

## Tools

Python, Pandas, NumPy, Matplotlib, Seaborn, statsmodels, scikit-learn,
Jupyter Notebook
