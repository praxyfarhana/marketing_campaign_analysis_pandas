# Analyzing Marketing Campaigns with pandas

## Project Objective

The objective of this project is to apply pandas and exploratory data analysis (EDA) techniques to a subscription business's marketing dataset in order to translate raw campaign data into actionable business insights. The analysis is structured around three core business questions:

1. **How did this campaign perform?**
   Calculate and visualize conversion rates across the campaign lifecycle to assess overall effectiveness.

2. **Which channel is referring the most subscribers?**
   Compare acquisition channels — Email, Instagram, Facebook, Push, and House Ads — to identify which are driving the most conversions.

3. **Why is a particular channel underperforming?**
   Break down conversion rates by key variables (day of week, age group, and language) to uncover patterns and root causes behind weaker channel performance.

## Dataset

The dataset (`marketing.csv`) contains user-level marketing exposure and subscription records, including:

| Column | Description |
|---|---|
| `user_id` | Unique customer identifier |
| `date_served` | Date the marketing message was displayed |
| `marketing_channel` | Channel used (Email, House Ads, Push, Instagram, Facebook) |
| `variant` | Ad variant shown (e.g., personalization) |
| `converted` | Whether the user converted (subscribed) |
| `language_displayed` / `language_preferred` | Ad language vs. user's preferred language |
| `age_group` | User's age bracket |
| `date_subscribed` / `date_canceled` | Subscription and cancellation dates |
| `subscribing_channel` | Channel through which the user subscribed |
| `is_retained` | Whether the user remained subscribed |

## Tools & Libraries

- **pandas** — data loading, cleaning, grouping, aggregation
- **NumPy** — numerical operations
- **matplotlib** / **seaborn** — data visualization
- **Google Colab** — development environment, with datasets accessed via Google Drive

## Methodology

1. **Data Loading & Inspection** — loaded the dataset and reviewed structure, data types, and summary statistics using `.info()` and `.describe()`.
2. **Data Cleaning**
   - Converted `date_served`, `date_subscribed`, and `date_canceled` to datetime format.
   - Classified columns into identifier vs. categorical types.
   - Checked for duplicate `user_id` entries.
   - Quantified missing values per column.
3. **Campaign Performance Analysis** — calculated the overall conversion rate across all channels.
4. **Channel Comparison** — grouped by `marketing_channel` to calculate and visualize conversion rate per channel.
5. **Root-Cause Diagnosis** — for underperforming channels (House Ads, Push), broke down conversion rate by:
   - Day of week
   - Age group
   - Language displayed

## Key Findings

- **Overall conversion rate:** 10.74%
- **Top performer:** Email — 34.16% conversion rate, far above all other channels
- **Mid-range performers:** Instagram (14.16%) and Facebook (12.74%)
- **Underperformers:** Push (8.36%) and House Ads (6.30%)
- **House Ads diagnosis:**
  - Conversion is fairly stable across days of the week (peak Wednesday, lowest Saturday)
  - Younger age groups (0–18, 24–30) convert noticeably better than older groups (30–36, 45–55)
  - Conversion rate varies sharply by language displayed, with English-speaking audiences underperforming relative to Arabic and German

## Recommendations

1. **Increase investment in Email marketing** given its significantly higher conversion rate.
2. **Re-target House Ads by language** — prioritize Arabic and German-speaking audiences; revisit creative/offers for English-speaking audiences.
3. **Refine age-group targeting** for House Ads and Push to focus budget on higher-converting segments.
4. **Further investigate the Push channel** using the same day-of-week, age, and language breakdowns applied to House Ads.

## Repository Structure

```
├── marketing_campaign_analysis.ipynb   # Main analysis notebook
├── data/
│   └── marketing.csv                   # Dataset (or link if too large for repo)
├── images/                             # Exported chart visuals
└── README.md                           # Project overview (this file)
```

## How to Run

1. Clone this repository.
2. Open `marketing_campaign_analysis.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
3. If using Colab, mount Google Drive and update the file path to point to your copy of `marketing.csv`.
4. Run all cells in order.

## Conclusion

This project applied pandas and exploratory data analysis to transform raw marketing campaign data into actionable business insights. By analyzing conversion rates, comparing channel performance, and diagnosing root causes behind underperformance, the analysis lays a foundation for optimizing future marketing spend — most notably, reallocating budget toward Email and refining targeting for House Ads and Push.
