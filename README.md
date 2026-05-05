# 🎮 Video Game Sales Analysis & Forecasting

## Overview
This project analyzes historical video game sales data to identify patterns that determine a game's commercial success. Working as an analyst for the fictional online store **Ice**, the goal is to uncover trends that can guide advertising campaign planning for 2017.

The dataset covers global game sales across platforms, genres, and regions from the 1980s through 2016.

---

## Tools & Libraries
- **Python** — core language
- **Pandas** — data manipulation and aggregation
- **NumPy** — numerical operations (e.g., rounding durations)
- **Matplotlib** — data visualization
- **SciPy** — statistical hypothesis testing

---

## Skills Demonstrated
- Data cleaning and type conversion
- Handling missing values and "TBD" entries
- Feature engineering (total sales column)
- Time-based filtering for relevant forecasting window
- Platform lifecycle analysis with year-over-year growth
- Regional market profiling (NA, EU, JP)
- Correlation analysis between review scores and sales
- Statistical hypothesis testing (Welch's t-test)

---

## Dataset
A single CSV file with records of video game releases:

| Column | Description |
|---|---|
| `name` | Game title |
| `platform` | Console/platform (e.g., PS4, XOne, PC) |
| `year_of_release` | Year the game was released |
| `genre` | Game genre (e.g., Action, Sports, RPG) |
| `na_sales` | North America sales (millions) |
| `eu_sales` | Europe sales (millions) |
| `jp_sales` | Japan sales (millions) |
| `other_sales` | Other regions sales (millions) |
| `critic_score` | Metacritic critic score (0–100) |
| `user_score` | Metacritic user score (0–10) |
| `rating` | ESRB rating (E, T, M, etc.) |

---

## Data Cleaning & Preprocessing
- Converted column names to lowercase
- Converted `year_of_release`, `critic_score`, and `user_score` to numeric using `errors='coerce'`
- Identified and separately counted `tbd` (to be determined) values in `user_score` before conversion
- Filled missing `name` and `genre` with `'Unknown'`; kept `year_of_release` and ratings as `NaN` to avoid distorting analysis
- Created a `total_sales` column as the sum of all regional sales

---

## Relevant Time Window
After examining game release trends over time, **2013–2016** was selected as the most relevant period for forecasting 2017 sales. Older data reflects outdated platforms and market conditions no longer applicable to the current landscape.

---

## Key Findings

### 📅 Platform Lifecycle
- Platforms follow a clear lifecycle — they rise, peak, and decline
- A heatmap of platform sales (2013–2016) shows which platforms dominated recent years
- Year-over-year (YoY) growth analysis of the top 5 platforms reveals which are growing vs. fading

### 🏆 Top Platforms (2013–2016)
- **PS4** and **XOne** led global sales in the relevant period
- Sales distributions are highly skewed — a small number of games account for most revenue

### 🔍 Review Scores vs. Sales (PS4)
- **Critic scores** show a moderate positive correlation with total sales
- **User scores** show a weaker relationship with sales
- Neither score alone predicts success reliably

### 🌍 Regional Differences
- **NA and EU** share similar platform and genre preferences
- **Japan** diverges significantly — stronger preference for Role-Playing games and handheld platforms
- Top genres globally: **Action** and **Shooter** dominate NA and EU; **Role-Playing** is strongest in JP

### 🎭 ESRB Ratings
- Rating impact varies by region
- Some rating categories sell significantly better in specific markets

---

## Hypothesis Tests

### Test 1 — Xbox One vs. PC User Ratings
- **H₀:** Average user ratings for Xbox One and PC are equal
- **H₁:** Average user ratings are different
- **Method:** Welch's two-sample t-test (α = 0.05)
- **Result:** Based on p-value vs. alpha threshold

### Test 2 — Action vs. Sports User Ratings
- **H₀:** Average user ratings for Action and Sports genres are equal
- **H₁:** Average user ratings are different
- **Method:** Welch's two-sample t-test (α = 0.05)
- **Result:** Based on p-value vs. alpha threshold

---

## How to Run
1. Clone the repository
2. Open `video-game-sales-forecasting.ipynb` in Jupyter Notebook or JupyterLab
3. Update the dataset file path if running locally (loads from `/datasets/games.csv`)
4. Run all cells in order

---

## Project Status
Completed as part of the **TripleTen Machine Learning & AI Bootcamp** — Exploratory Data Analysis sprint.
