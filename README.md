## Digital Marketing Analytics Dashboard

### Project Overview

This project analyzes a Digital Marketing Dataset from Kaggle, providing insights into customer interactions with digital marketing campaigns. The dataset includes demographic data, marketing-specific metrics, customer engagement indicators, and historical purchase data. The goal was to develop an interactive Power BI dashboard that empowers data-driven marketing decisions by analyzing the performance and effectiveness of 2024 campaigns.

📂 Dataset Source: [Kaggle - Digital Marketing Dataset](https://www.kaggle.com/datasets/rabieelkharoua/predict-conversion-in-digital-marketing-dataset)

🚀 Tech Stack

Power BI & DAX


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

- 18-19 y.o.
- 20-29 y.o.
- 30-39 y.o.
- 40-49 y.o.
- 50-59 y.o.
- 60-69 y.o. 

### Dashboards & Insights

Three interactive dashboards were created for in-depth marketing analytics:

🔹 1. Conversion Rate Analysis

This dashboard provides a comprehensive view of five primary campaign channels, breaking down key metrics including cost, total customers, conversion rate, and customer acquisition cost. The main feature is a scatter plot that illustrates the relationship between conversion rate and total spend for each campaign channel. Additionally, interactive card visuals allow you to dynamically explore different metrics—total spend, total customers, and conversion rate—by simply clicking through the options.

![image](https://github.com/user-attachments/assets/d3fa434e-083b-46f1-80f5-3832f3762309)


🔹 2. Customer Demographics Analysis

In this section, we analyze total conversions and spend across different customer age groups. The dashboard provides insights into the number of customers and their respective conversion rates, helping to identify which age groups are most engaged and valuable.

![image](https://github.com/user-attachments/assets/a2d492e2-98ee-41cc-9b7a-cf69e2593f7c)


🔹 3. Website Visits & Engagement

Here, we examine the relationship between total website visits and average time spent on the site by different age groups. A pie chart with filtering functionality shows which users spent more than one minute on the site, offering deeper insights into engagement. Card visuals display the average Click-Through Rate (CTR) and Cost Per Click (CPC) for a more granular view of campaign performance.

![image](https://github.com/user-attachments/assets/c77aec6b-0ef5-4ffd-acb6-e4c980e65cf1)


📥 How to Use the Dashboard

- Download the Power BI file (to be added once published)
- Open it in Power BI Desktop
- Explore the interactive dashboards

### Main Takeaways for Stakeholders:

1. Campaign Effectiveness: Unfortunately, the overall campaign effectiveness was low, with a conversion rate of just 0.0175%. Despite this, the total spend was disproportionately high.
2. High Conversion Rates, Low Effectiveness: Although conversion rates were high, indicating that many customers who engaged with campaigns did convert, the overall effectiveness didn’t yield strong results.
3. Target Audience Insight: There was a notably lower participation rate among 18-19-year-olds, suggesting that they may not be the ideal target group for these campaigns.
4. Age Group Performance: The highest conversion rates came from the 30-39-year-old demographic, which could be the most lucrative target audience.
5. Campaign Channel Costs: The Referral campaign channel was the most expensive, while Social Media proved to be the most cost-effective channel.
6. Spend vs Conversion Rate: There is a clear correlation between higher total spend and increased conversion rates, making it evident that increased investment led to better performance, although the overall effectiveness remains low.


📧 Contact

For any queries or suggestions, feel free to reach out via GitHub issues or email.

🔗 Author: Nadia Usalko 📩 Email: nadia.usalko@gmail.coml🔗 LinkedIn: [Nadia Usalko](https://www.linkedin.com/in/Nadia-usalko/)

