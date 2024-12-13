# The Project
For this project, Kunal and I went on a deep dive through this dataset that we found on [Kaggle](https://www.kaggle.com/datasets/gbolduc/fantasy-football-data-2017-2023)

[<---](https://maxfleming05.github.io/)
---

Google Colab Document
[Document](/Final_Project.ipynb)

---
 # Analysis of Fantasy Football Data (2017-2022)

The dataset we are exploring contains football statistics on quarterbacks, wide receivers, running backs, and tight ends from the 2017-2022 seasons. This dataset was found on Kaggle and contains **3389 rows** and **27 columns** of data, featuring important statistics such as interceptions, touchdowns, fumbles, passing yards, and receiving yards.

We aimed to examine the correlation between specific metrics (e.g., receiving or throwing yard statistics) and the **total fantasy football points (PPR)** at the end of the season. The statistics we analyzed include:

- Rushing yards per attempt
- Completion percentage
- Rushing yards per touchdown
- Receiving yards per touchdown
- Receiving yards per catch

### Objectives
1. **Visualize** statistical metrics against total fantasy points.
2. **Calculate** correlations between chosen metrics and PPR.
3. **Predict** top performers for the 2022 season using correlation data and validate predictions with actual 2022 data.

---

## Data Preparation

To prepare the data, we:

1. Used **Pandas** to create new columns: `CompPct`, `RushYds/TD`, and `RecYds/TD`.
2. Filtered the data by positions (Quarterbacks, Wide Receivers, and Running Backs).
3. Visualized the distribution of total yards per player in each subset using a histogram. 

Most data entries were near zero. To address this, we analyzed only the **top 50% of players** in each category. The distributions of rushing, receiving, and passing yards are shown below:

{% include_relative Distribution_of_Rushing_Yards.html %}


{% include_relative Distribution_of_Receiving_Yards.html %}


{% include_relative Distribution_of_Passing_Yards.html %}


## Quarterbacks

We started by examining the **completion percentage** as total throwing yards alone would directly correlate with PPR. The scatter plot of completion percentage against PPR is displayed below:

{% include_relative Scatter_CompPCT_PPR.html %}

### Observations
- The correlation between completion percentage and PPR was **0.19**.
- This weak correlation suggests that completion percentage is not a reliable predictor of a quarterback's fantasy performance.


## Wide Receivers

### Receiving Yards per Reception
We plotted **receiving yards per reception** (provided in the dataset) against PPR:

{% include_relative Scatter_YA_PPR.html %}

#### Observations
- The correlation was only **0.01**, indicating almost no relationship.
- This result aligns with expectations: good players often have high reception counts, but not all receptions yield significant yardage.


### Receiving Yards per Touchdown
Next, we examined the correlation between **receiving yards per touchdown** and PPR. Receiving yards were divided by touchdowns to compute this metric. The scatter plot is below:

{% include_relative Scatter_YardsperTouchdown_PPR.html %}

#### Observations
- The correlation was **-0.17**, a weak negative correlation.
- This suggests that a high number of touchdowns often results in fewer yards per touchdown but does not directly translate to a higher PPR.


## Running Backs

### Rushing Yards per Attempt
We analyzed **rushing yards per rushing attempt** and compared them to PPR. The scatter plot is displayed below:

{% include_relative Scatter_YR_PPR.html %}

#### Observations
- The correlation was **0.12**, another weak correlation.
- Players with high rushing attempts don’t necessarily achieve high yards per attempt due to variability in individual plays.


### Rushing Yards per Touchdown
Finally, we compared **rushing yards per touchdown** against PPR:

{% include_relative Scatter_YardsRushingTouchdown_PPR.html %}

#### Observations
- The correlation was **-0.18**, a weak negative correlation.
- High-touchdown players often have lower yards per touchdown due to frequent usage in the red zone.


## Key Findings

After analyzing fantasy football data from 2017-2022:
- The highest correlation observed was **0.19** (completion percentage vs PPR).
- Scatter plots displayed no visible trends, appearing nearly random.

These results indicate that predicting top performers using the analyzed statistics alone would be highly uncertain.


## Limitations and Future Directions

### Challenges
1. **Low Correlation Values**: Metrics like rushing yards per attempt and receiving yards per touchdown had weak or negative correlations with PPR.
2. **Data Gaps**: The dataset only extends to 2022, limiting the relevance of findings to the current season.

### Potential Improvements
- **Incorporating Additional Metrics**: A third axis, such as total yards, could provide richer context.
- **Expanding the Dataset**: Including 2023 and 2024 data could enhance the accuracy of predictions for the 2025 season.

Despite our efforts, the lack of significant correlations suggests that identifying a simple predictor of fantasy football success may not be feasible. Future studies could explore more complex statistical models or additional datasets to uncover deeper insights.

[<---](https://maxfleming05.github.io/)
---
