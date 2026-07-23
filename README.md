# Spotify Song Popularity — Exploratory Data Analysis

Exploratory data analysis examining which track and playlist features relate to
song popularity, using the Spotify Songs dataset from
[TidyTuesday](https://github.com/rfordatascience/tidytuesday/tree/main/data/2020/2020-01-21) (~32,833 tracks).
Completed as coursework for an M.S. in Data Science program. This EDA phase lays
the groundwork for an upcoming predictive modeling phase.

## Dataset

- Source: TidyTuesday Spotify Songs dataset
- ~32,833 tracks
- Outcome variable: `track_popularity`, logit-transformed to prepare it for a
  later linear regression model

## Methods

- Data loading and cleaning with Pandas and NumPy
- Focused the analysis on 8 variables:
  - Categorical: `playlist_genre`, `playlist_subgenre`
  - Continuous: `danceability`, `energy`, `loudness`, `instrumentalness`,
    `valence`, `tempo`
- Summary statistics for each variable and the transformed outcome
- Visualizations built with Matplotlib and Seaborn:
  - Bar charts for categorical distributions
  - Histograms / KDE plots for continuous distributions
  - Faceted violin plots for grouped comparisons across genres and subgenres
  - Scatter plots with regression lines
  - A correlation heatmap across continuous variables

## Key Findings

- Playlist genre and subgenre influenced song popularity more than any single
  continuous audio feature
- Secondary relationships emerged between energy and loudness, and between
  valence and danceability
- Popularity consistency varied at the subgenre level even within genres that
  looked consistent overall (e.g., Rock)

## Next Steps

A predictive modeling phase — a linear regression model on the
logit-transformed popularity variable — is planned as a follow-up to this EDA.

## Tools

Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook
