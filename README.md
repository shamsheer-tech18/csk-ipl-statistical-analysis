# Impact of Key Factors on Team Success in India's Cricket Sport League — IPL

### Chennai Super Kings (CSK) Performance Analysis (2020–2024)

![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![Minitab](https://img.shields.io/badge/Minitab-007ACC?style=flat&logo=data:image/svg+xml;base64,&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

> **Course:** IE 6200 — Engineering Probability & Statistics  
> **University:** Northeastern University, Mechanical & Industrial Engineering Department  
> **Professor:** Rehab Ali · **Term:** Spring 2025  

---

## Overview

This project applies inferential statistics to investigate what genuinely drives match outcomes for the Chennai Super Kings (CSK) in the Indian Premier League (IPL). Using match-level data spanning five seasons (2020–2024) and 76 matches, we performed descriptive analysis, hypothesis testing, confidence interval estimation, and ANOVA to quantify the influence of powerplay scoring, toss decisions, venue characteristics, and seasonal trends on CSK's win probability.

---

## Problem Statement

The Indian Premier League is a franchise-based Twenty20 cricket league where two 11-player teams compete in a fast-paced, 20-over-per-side format. While conventional wisdom often attributes match outcomes to factors like toss advantage or home-ground familiarity, empirical validation of these claims is limited. This project poses the question: **What measurable factors significantly influence CSK's match success?** We use statistical inference to separate genuine performance drivers from noise.

---

## Key Findings

| # | Finding | Statistical Evidence |
|---|---------|---------------------|
| 1 | **Powerplay performance is a strong predictor of match outcome.** Winning matches had a median powerplay score of 50.6 runs vs. 43.3 in losses. | Boxplot comparison; 95% CI for powerplay in wins: 45.64–52.46 runs |
| 2 | **Toss outcome does NOT significantly affect match result.** CSK won 18 matches after winning the toss and 21 matches after losing it. | Mosaic plot; win percentage after toss win: 57.6% (95% CI: 40.1%–73.3%) |
| 3 | **CSK performs significantly better chasing (batting second).** Win proportion clusters at 0.35–0.40 when batting second vs. below 0.25 when batting first. | Sampling distribution of proportions |
| 4 | **First innings scoring varies significantly across seasons.** | One-way ANOVA: F(4, 60) = 3.27, p = 0.016 — null hypothesis rejected |
| 5 | **Venue has a statistically significant impact on scoring.** Chennai's MA Chidambaram (CI: 160–190) vs. Ahmedabad's Narendra Modi Stadium (CI: 177–238). | Confidence intervals by venue (p = 0.009) |
| 6 | **First innings score difference between wins and losses is NOT statistically significant.** | Difference = 5.4 runs, p = 0.610 |

---

## Dataset

| Attribute | Detail |
|-----------|--------|
| **Sources** | [Kaggle IPL Dataset](https://www.kaggle.com/datasets), Howstat, Official IPL Website |
| **Scope** | Chennai Super Kings, 5 seasons (2020–2024), 76 matches |
| **Format** | CSV |

### Key Variables

| Variable | Type | Description |
|----------|------|-------------|
| Season | Independent | IPL season year (2020–2024) |
| First Innings Score | Dependent | Total runs scored batting first |
| Second Innings Score | Dependent | Total runs scored batting second |
| Powerplay Score | Dependent | Runs scored in overs 1–6 |
| Middle Overs Score | Dependent | Runs scored in overs 7–15 |
| Death Overs Score | Dependent | Runs scored in overs 16–20 |
| Win Margin | Dependent | Margin of victory (runs or wickets) |
| Opponent | Categorical | Opposing team name |
| Venue | Categorical | Stadium where match was played |
| Toss Winner | Categorical | Team that won the coin toss |
| Toss Decision | Categorical | Bat first or field first |
| Match Winner | Categorical | Team that won the match |
| Win Type | Categorical | Won by runs or by wickets |

---

## Methodology

### 1. Data Visualization
- **Trophy distribution chart** — IPL titles by franchise (2008–2024)
- **Season-wise win/loss bar charts** — CSK's record across 5 seasons
- **Mosaic plot** — Toss outcome vs. match result dependency
- **Boxplots** — Powerplay scores in wins vs. losses
- **Line plots** — First innings score trends across seasons
- **Scatter plot with regression** — Correlation between powerplay and first innings scores (r = 0.46)

### 2. Sampling Distributions
- **Powerplay scores** — Bell-shaped distribution centered around 48 runs (validates CLT)
- **Death over scores** — Right-skewed distribution indicating explosive but inconsistent late scoring
- **Win proportions** — Batting first vs. batting second comparison

### 3. Confidence Intervals
- **CI of Mean:** Powerplay scores in wins → 95% CI: [45.64, 52.46]
- **CI of Mean by Venue:** Chennai (160–190), Mumbai (139–189), Ahmedabad (177–238)
- **CI of Difference of Means:** First innings score in wins vs. losses → difference = 5.4, p = 0.610 (not significant)
- **CI of Proportions:** Win percentage after winning toss → 57.6%, 95% CI: [40.1%, 73.3%]

### 4. Hypothesis Testing
- **Two-sample t-test** comparing first innings scores in wins vs. losses
- **Proportion test** for toss advantage significance
- **Additional tests** on batting-first vs. chasing success rates

### 5. ANOVA
- **One-way ANOVA** on first innings scores across seasons (2020–2024)
  - F(4, 60) = 3.27, p = 0.016 → Reject H₀; seasons differ significantly
- **Tukey's HSD post-hoc** to identify which season pairs differ
  - 2020 performance significantly lower than 2022, 2023, and 2024 (p < 0.01)

---

## Selected Visualizations

> **Note:** All figures are available in the `figures/` directory.

| Figure | Description |
|--------|-------------|
| `fig01_ipl_trophies.png` | IPL trophies won by each franchise (2008–2024) |
| `fig02_wins_losses_by_season.png` | CSK wins and losses across 5 seasons |
| `fig03_mosaic_toss_match.png` | Mosaic plot — toss outcome vs. match result |
| `fig04_powerplay_boxplot.png` | Boxplot comparing powerplay scores in wins vs. losses |
| `fig05_first_innings_trend.png` | First innings scores across seasons |
| `fig06_powerplay_correlation.png` | Scatter plot — powerplay vs. first innings score (r = 0.46) |
| `fig07_sampling_dist_mean.png` | Sampling distribution of mean powerplay scores |
| `fig08_anova_boxplot.png` | ANOVA boxplot — first innings by season |
| `fig09_tukey_hsd.png` | Tukey's simultaneous 95% confidence intervals |

---

## Project Structure

```
ie6200-ipl-csk-statistical-analysis/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── reports/
│   ├── Phase1_Project_Proposal.pdf
│   ├── Phase2_Progress_Report.pdf
│   └── Phase3_Final_Report.pdf
│
├── presentation/
│   └── Final_Presentation.pptx
│
├── data/
│   ├── raw/
│   │   └── ipl_csk_matches_2020_2024.csv
│   └── cleaned/
│       └── ipl_csk_cleaned.csv
│
├── code/
│   ├── 01_data_cleaning.R
│   ├── 02_data_visualization.R
│   ├── 03_sampling_distributions.R
│   ├── 04_confidence_intervals.R
│   ├── 05_hypothesis_testing.R
│   └── 06_anova.R
│
├── figures/
│   ├── fig01_ipl_trophies.png
│   ├── fig02_wins_losses_by_season.png
│   ├── fig03_mosaic_toss_match.png
│   ├── fig04_powerplay_boxplot.png
│   ├── fig05_first_innings_trend.png
│   ├── fig06_powerplay_correlation.png
│   ├── fig07_sampling_dist_mean.png
│   ├── fig08_anova_boxplot.png
│   └── fig09_tukey_hsd.png
│
└── minitab/
    └── ipl_analysis.mpx
```

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| **R / RStudio** | Data cleaning, visualization (ggplot2), statistical tests |
| **Minitab** | Confidence intervals, hypothesis testing, ANOVA |
| **Microsoft Excel** | Preliminary data exploration and cleaning |
| **ggplot2** | Publication-quality visualizations |
| **dplyr / tidyr** | Data wrangling |

---

## Limitations

- **Sample size:** Analysis limited to 76 matches over 5 seasons; a larger dataset spanning CSK's full IPL history (2008–2024) could strengthen conclusions.
- **External factors excluded:** Weather conditions, player injuries, auction strategies, and team composition changes were not modeled.
- **Single-team focus:** Findings are specific to CSK and may not generalize to other IPL franchises.

## Future Work

- Incorporate player-level metrics (economy rates, strike rates, batting averages)
- Model phase-wise strategies using regression analysis
- Integrate weather and pitch condition data
- Build scenario-based match simulations
- Extend analysis framework to other IPL teams for comparative study

---

## References

[1] Kaggle, "IPL Dataset," [Online]. Available: https://www.kaggle.com/datasets. [Accessed: 2025].  
[2] Howstat, "IPL Cricket Statistics," [Online]. Available: https://www.howstat.com. [Accessed: 2025].  
[3] Indian Premier League, "Official IPL Website," [Online]. Available: https://www.iplt20.com. [Accessed: 2025].  
[4] R. E. Walpole, R. H. Myers, S. L. Myers, and K. Ye, *Probability and Statistics for Engineers and Scientists*, 9th ed. Boston, MA: Pearson, 2011.

---

## License

This project is shared for educational and portfolio purposes. All data is publicly available from the sources cited above.
