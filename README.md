## Digital Marketing Analytics Dashboard

### Project Overview

This project analyzes a Digital Marketing Dataset from Kaggle, providing insights into customer interactions with digital marketing campaigns. The dataset includes demographic data, marketing-specific metrics, customer engagement indicators, and historical purchase data. The goal was to develop an interactive Power BI dashboard that empowers data-driven marketing decisions by analyzing the performance and effectiveness of 2024 campaigns.

📂 Dataset Source: [Kaggle - Digital Marketing Dataset](https://www.kaggle.com/datasets/rabieelkharoua/predict-conversion-in-digital-marketing-dataset)

🚀 Tech Stack

Power BI (Data Visualization & Analysis)
DAX (Data Analysis Expressions for calculated measures & columns)
Data Cleaning & Transformation (within Power BI)


🔗 Dashboard Link: (Will be added once published)

📊 Key Metrics & Calculated Measures

The following calculated measures were created using DAX:

### Measures

Total Amount Spent – Total budget spent on campaigns

```DAX
total_amount_spent = SUM(digital_marketing_campaign_dataset[AdSpend_USD])
```

Total Conversions – Number of successful conversions
```DAX
total_conversions = 
SUM(digital_marketing_campaign_dataset[Conversion])
```


Total Clicks – Count of ad clicks
```DAX
total_clicks = 
SUM('digital_marketing_campaign_dataset'[WebsiteVisits])
```

Conversion Rate – Percentage of users who converted. The dataset only presented binary data - 1/0.
```DAX
conversion_rate = 
DIVIDE(
    COUNTROWS(
        FILTER(
            'digital_marketing_campaign_dataset',
            'digital_marketing_campaign_dataset'[conversion_binary] IN { "True", "Yes", "TRUE" }
        )
    ),
    COUNTROWS('digital_marketing_campaign_dataset'),
    0
)
```


Cost Per Click (CPC) – Total Amount Spent / Total Clicks
```DAX
cost_per_click = 
DIVIDE(
    SUM('digital_marketing_campaign_dataset'[AdSpend_USD]),
    [total_clicks],
    0
)
```


Customer Acquisition Cost (CAC) – Total Amount Spent / Total Conversions
```DAX
customer_acquisition_cost = 
DIVIDE(
    [total_amount_spent],
    [total_conversions],
    0
)
```

Campaign Effectiveness Ratio 
```DAX
campaign_effectiveness_ratio = 
DIVIDE(
    [total_conversions],
    [total_amount_spent],
    0
)
```

📌 Conditional Column:

Age Group Classification – a reference table was created with a conditional column in order to conduct analysis of customers by age.

Customers grouped into:

- 18-20 years
- 21-30 years
- 31-40 years
- 41-50 years
- 51-60 years


### Dashboards & Insights

Three interactive dashboards were created for in-depth marketing analytics:

🔹 1. Conversion Rate Analysis

Breakdown of conversion rates by different marketing channels

Insights into Customer Acquisition Cost (CAC)

Campaign performance comparison

🔹 2. Customer Demographics Analysis

Breakdown of customers by age group

Analysis of campaign effectiveness ratio

Customer trends based on demographics

🔹 3. Website Visits & Engagement

Average time spent on site

Click-Through Rate (CTR) analysis

Cost Per Click (CPC) insights




📥 How to Use the Dashboard

- Download the Power BI file (to be added once published)
- Open it in Power BI Desktop
- Explore the interactive dashboards




📧 Contact

For any queries or suggestions, feel free to reach out via GitHub issues or email.

🔗 Author: Nadia Usalko 📩 Email: nadia.usalko@gmail.coml🔗 LinkedIn: [Nadia Usalko](https://www.linkedin.com/in/Nadia-usalko/)

