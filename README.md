# AB Testing (Marketing Campaigns)

## Project Overview
As a marketing agency, our goal is to maximize the **return on investment (ROI)** for our clients' advertising campaigns. This project analyzes and compares the performance of two ad campaigns conducted in 2019—one on **Facebook** and the other on **AdWords**—to determine which platform delivers better results in terms of **clicks, conversions, and cost-effectiveness**. Insights from this analysis help allocate resources efficiently and optimize advertising strategies.

## Business Problem
The marketing team needs to identify the most effective advertising platform to improve campaign performance. By understanding which platform drives more conversions and clicks at a lower cost, the agency can improve ROI and make data-driven decisions for future campaigns.

**Research Question:** Which ad platform is more effective in terms of **conversions, clicks, and overall cost-effectiveness**?

## Libraries Used
- `pandas`
- `matplotlib`
- `seaborn`
- `scipy.stats`
- `numpy`
- `sklearn` (LinearRegression, metrics)
- `statsmodels` (seasonal_decompose, coint)
- `warnings`

## Data Description
The dataset contains daily performance metrics for Facebook and AdWords campaigns throughout 2019 (365 rows). Key features include:

- **Date:** From January 1st to December 31st, 2019.
- **Ad Views:** Number of times the ad was displayed.
- **Ad Clicks:** Number of clicks received.
- **Ad Conversions:** Number of successful conversions.
- **Cost per Ad:** Cost of running the ad campaign.
- **Click-Through Rate (CTR):** Clicks divided by views.
- **Conversion Rate:** Conversions divided by clicks.
- **Cost per Click (CPC):** Average cost per click.

## Exploratory Data Analysis

### Distribution of Clicks and Conversions
Histograms of clicks and conversions show a roughly **symmetrical distribution**, indicating no major outliers.  

**Facebook Clicks and Conversions**
![Facebook Clicks](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/186eb7d78b685fe5f62bb6d2d5763ca879d2a061/facebook_clicks.png)
![Facebook Conversions](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/186eb7d78b685fe5f62bb6d2d5763ca879d2a061/facebook_conversions.png)

**AdWords Clicks and Conversions**
![AdWords Clicks](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/186eb7d78b685fe5f62bb6d2d5763ca879d2a061/adwords_clicks..png)
![AdWords Conversions](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/75c3536bb3b935b3686b6db9ea1ff08c1c39c56d/adwords_conversions.png)

### Frequency of High-Converting Days
Bar chart comparing daily conversion frequencies for Facebook and AdWords:

![Daily Conversion Frequency](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/186eb7d78b685fe5f62bb6d2d5763ca879d2a061/daily_conversion_frequency.png)

### Correlation Analysis
- Facebook: **0.87** (strong correlation between clicks and conversions)  
- AdWords: **0.45** (moderate correlation)

![Correlation Comparison](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/75c3536bb3b935b3686b6db9ea1ff08c1c39c56d/correlation_comparison.png)

> Facebook ads are more effective in driving conversions.

## Hypothesis Testing
**Hypothesis:** Facebook ads will yield more conversions than AdWords ads.

- **Null Hypothesis (H0):** There is no difference in conversions or AdWords has equal or more conversions than Facebook.  
- **Alternative Hypothesis (H1):** Facebook has more conversions than AdWords.

**Results:**
- Mean conversions: Facebook = 11.74, AdWords = 5.98
- T-test p-value ≈ 9.35e-134

**Conclusion:** p-value < 0.05 → Reject H0. Facebook ads significantly outperform AdWords in conversions.

## Regression Analysis
Linear Regression predicts Facebook ad conversions based on clicks:

- **R² Score:** 76.35%
- **Mean Squared Error:** 2.02

**Predicted Conversions:**
- 50 clicks → 13 conversions
- 80 clicks → 19 conversions

**Scatter plot with regression line**
![Regression Analysis](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/186eb7d78b685fe5f62bb6d2d5763ca879d2a061/regression_analysis.png)

> This helps plan campaign goals, optimize ad spend, and forecast ROI.

## Time Series Analysis
- **Weekday trends:** Mondays and Tuesdays have the highest conversions.  
- **Monthly trends:** Overall upward trajectory; dips in Feb, Apr, May, Jun, Aug, Nov.  
- **Cost per Conversion (CPC):** Generally stable; lowest in May & Nov, highest in Feb.  

**Conversions over Months**
![Monthly Conversions](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/186eb7d78b685fe5f62bb6d2d5763ca879d2a061/monthly_conversions.png)

**CPC Trends**
![CPC Trends](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/186eb7d78b685fe5f62bb6d2d5763ca879d2a061/cpc_trends.png)

> Strategic budget allocation during low-CPC months can maximize ROI.

## Cointegration Analysis
- Long-term equilibrium relationship exists between **advertising spend and conversions**.  
- p-value << 0.05 → Stable proportional impact of budget changes on conversions.  

![Cointegration Test](https://github.com/asif684/A-B-Testing-Analysis-Facebook-VS-Adword-/blob/186eb7d78b685fe5f62bb6d2d5763ca879d2a061/cointegration_test.png)

> Helps marketers optimize campaigns efficiently.

## Key Takeaways
1. Facebook ads generate more conversions than AdWords.  
2. High-conversion days occur more frequently on Facebook.  
3. Clicks strongly influence conversions on Facebook (R² = 76.35%).  
4. CPC trends indicate months suitable for strategic ad investment.  
5. Advertising spend and conversions have a long-term stable relationship.

## Conclusion
AB testing analysis shows **Facebook campaigns outperform AdWords** in conversions and cost-effectiveness. Marketers should focus resources on Facebook, monitor campaign performance, and adjust strategies to maximize ROI.

