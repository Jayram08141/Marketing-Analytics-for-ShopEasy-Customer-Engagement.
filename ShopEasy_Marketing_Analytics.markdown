# Marketing Analytics Portfolio Project: ShopEasy Customer Engagement Analysis

## Project Overview
This project was undertaken to address critical business challenges faced by ShopEasy, an online retail business experiencing declining customer engagement, reduced conversion rates, and suboptimal returns on marketing investments. The objective was to conduct a comprehensive analysis of customer feedback, social media comments, and campaign performance data to uncover actionable insights, optimize marketing strategies, and enhance customer satisfaction.

## Business Problem
ShopEasy observed:
- **Reduced Customer Engagement**: A decline in interactions with the website and marketing content.
- **Decreased Conversion Rates**: Fewer site visitors converting into paying customers.
- **High Marketing Expenses**: Significant investments in marketing campaigns not yielding expected returns.
- **Need for Customer Feedback Analysis**: A critical requirement to understand customer sentiments to improve engagement and conversions.

The project aimed to identify factors impacting conversion rates, determine high-performing content types, and extract insights from customer feedback to guide product and service improvements.

## Key Performance Indicators (KPIs)
- **Conversion Rate**: Percentage of website visitors making a purchase.
- **Customer Engagement Rate**: Level of interaction with marketing content (clicks, likes, comments).
- **Average Order Value (AOV)**: Average amount spent per transaction.
- **Customer Feedback Score**: Average rating from customer reviews.

## Goals
1. **Increase Conversion Rates**: Identify drop-off points in the conversion funnel and recommend optimizations.
2. **Enhance Customer Engagement**: Analyze content performance to inform effective content strategies.
3. **Improve Customer Feedback Scores**: Identify recurring themes in reviews to guide product and service enhancements.

## Methodology
The project leveraged a robust data analytics pipeline using SQL, Python, and Power BI to process, clean, and analyze data, followed by actionable recommendations derived from insights.

### Data Preparation and Cleaning (SQL)
- **Customer Data Enrichment**: Joined `dim_customers` with `dim_geography` to incorporate geographic information (Country, City) for demographic analysis.
- **Product Categorization**: Categorized products into Low (<$50), Medium ($50-$200), and High (>$200) price categories using a CASE statement in `dim_products.sql`.
- **Customer Reviews Cleaning**: Standardized `ReviewText` in `fact_customer_reviews.sql` by replacing double spaces with single spaces for improved readability.
- **Customer Journey Deduplication**: Used a Common Table Expression (CTE) in `fact_customer_journey.sql` to identify and remove duplicate records, ensuring data integrity by retaining only the first occurrence of each unique customer interaction.
- **Engagement Data Normalization**: Cleaned `fact_engagement_data.sql` by standardizing `ContentType` (e.g., converting "Socialmedia" to "Social Media"), splitting `ViewsClicksCombined` into separate `Views` and `Clicks` columns, and formatting `EngagementDate` to a consistent `dd.MM.yyyy` format. Excluded irrelevant Newsletter data.

### Sentiment Analysis (Python)
- Developed a Python script (`customer_reviews_enrichment.py`) using Pandas and NLTK’s VADER SentimentIntensityAnalyzer to analyze customer reviews.
- Calculated sentiment scores (`SentimentScore`) ranging from -1 (negative) to 1 (positive).
- Categorized sentiments into Positive, Negative, Neutral, Mixed Positive, and Mixed Negative based on both sentiment scores and review ratings.
- Bucketed sentiment scores into ranges (e.g., 0.5 to 1.0 for strongly positive) for granular analysis.
- Saved enriched data to `fact_customer_reviews_with_sentiment.csv` for further analysis.

### Calendar Table Creation (DAX)
- Created a `Calendar` table in Power BI using DAX to facilitate time-based analysis, including columns for Date, Year, Month, Quarter, and Day of Week, covering January 1, 2023, to December 31, 2025.

### Data Visualization and Reporting (Power BI)
- Designed interactive dashboards to visualize KPIs, conversion trends, engagement metrics, and customer feedback distributions.
- Analyzed seasonal trends, content performance, and sentiment distributions to derive actionable insights.

## Key Findings
### Conversion Rates
- Conversion rates fluctuated, peaking at 18.5% in January (driven by high-performing products like Ski Boots at 150%) and dipping to 4.3% in May, indicating seasonal variability and underperforming periods.
- December showed a rebound to 10.2%, suggesting recovery potential with targeted interventions.

### Customer Engagement
- Social media views peaked in February and July but declined from August onward, indicating reduced audience engagement in the latter half of the year.
- Clicks and likes were consistently low compared to views, with a click-through rate of 15.37%, suggesting engaged users interact effectively but overall interaction rates need improvement.
- Blog content drove the highest views, particularly in April and July, while social media and video content showed steady but lower engagement.

### Customer Feedback
- Customer ratings averaged 3.7, below the target of 4.0, indicating room for improvement.
- Sentiment analysis revealed 275 positive reviews, 82 negative, and a mix of neutral and mixed sentiments, reflecting a generally satisfied customer base with specific areas for enhancement.
- Common positive themes included quick delivery, high product quality, and helpful customer support.
- Recurring negative themes included high pricing, unclear instructions, late deliveries, and product durability issues.

## Actionable Recommendations
### Increase Conversion Rates
- **Target High-Performing Products**: Focus marketing efforts on products with strong conversion rates (e.g., Kayaks, Ski Boots, Baseball Gloves) through seasonal promotions and personalized campaigns, especially in high-performing months like January and September.
- **Optimize Conversion Funnel**: Analyze drop-off points in the customer journey (e.g., checkout or product page abandonment) and implement improvements like streamlined checkout processes or enhanced product descriptions.

### Enhance Customer Engagement
- **Revitalize Content Strategy**: Experiment with interactive videos and user-generated content to boost engagement. Optimize call-to-action placement in social media and blog content, particularly during low-engagement months (September–December).
- **Leverage High-Performing Content**: Increase investment in blog content, which drives the most views, and test new formats to sustain engagement year-round.

### Improve Customer Feedback Scores
- **Address Negative Feedback**: Implement a feedback loop to analyze mixed and negative reviews, focusing on common issues like pricing, instructions, delivery delays, and durability. Develop targeted improvement plans, such as clearer product guides or faster shipping options.
- **Engage Dissatisfied Customers**: Follow up with customers who left mixed or negative reviews to resolve issues and encourage re-rating, aiming to elevate the average rating to 4.0.

## Technologies Used
- **SQL**: Data extraction, cleaning, and transformation.
- **Python (Pandas, NLTK)**: Sentiment analysis and data enrichment.
- **Power BI (DAX)**: Data visualization and reporting.
- **Database**: SQL Server (PortfolioProject_MarketingAnalytics).

## Key Skills Demonstrated
- **Data Cleaning and Preparation**: Standardized and deduplicated datasets to ensure data quality.
- **Sentiment Analysis**: Applied NLP techniques to extract customer sentiments and categorize feedback.
- **Data Visualization**: Created impactful dashboards to communicate insights effectively.
- **Business Analysis**: Translated data insights into actionable business recommendations.
- **Cross-Functional Collaboration**: Integrated SQL, Python, and Power BI to deliver a comprehensive analytics solution.

## Impact
This project provided ShopEasy with a clear understanding of customer behavior, content performance, and areas for improvement. The actionable recommendations aim to boost conversion rates, enhance engagement through targeted content strategies, and improve customer satisfaction by addressing feedback concerns, ultimately driving better ROI on marketing investments.