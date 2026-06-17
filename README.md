# Customer Behaviour Analysis & Business Intelligence Pipeline

## Project Overview

This repository contains an end-to-end data analytics and business intelligence pipeline designed to evaluate retail purchasing trends, segment customer cohorts, and optimize revenue generation strategies.

By mapping the multidimensional relationships between customer demographics, purchase frequency, and seasonal product affinities, this project translates raw transactional data into an interactive executive dashboard.

## Project Architecture

The pipeline is divided into three distinct operational phases:

Data Engineering & EDA (Python): Ingesting, cleaning, and imputing missing data using pandas, followed by statistical visualizations using matplotlib and seaborn.

Relational Data Warehousing (PostgreSQL): Utilizing sqlalchemy and psycopg2 to load the cleaned DataFrame into a PostgreSQL fact table (customer_behaviour_analysis) for complex SQL aggregations.

Data Democratization (Power BI): Connecting the database directly to Power BI to engineer an interactive dashboard highlighting Key Performance Indicators (KPIs).

## Repository Structure
```
├── data/
│   └── customer_shopping_behavior.csv    
├── EDA.ipynb                     
├── business_queries.sql              
├── Customer_behaviour_analysis.pbix    
├── .env
├── requirements.txt                      # Python dependency list
└── README.md                             # Project documentation
```

## Prerequisites & Setup

To replicate this project locally, ensure you have Python 3.8+, PostgreSQL, and Power BI Desktop installed.

1. Clone the Repository
```
git clone [https://github.com/yourusername/customer-behaviour-analysis.git](https://github.com/yourusername/customer-behaviour-analysis.git)
cd customer-behaviour-analysis
```

2. Set Up the Virtual Environment
```
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt
```

3. Configure Database Credentials

This project uses ```python-decouple``` to securely manage database credentials.

Update the .env file with your local PostgreSQL credentials:

```
DB_USER=your_postgres_username
DB_PSWD=your_postgres_password
DB_HOST=localhost
DB_PORT=5432
DB_NAME=your_database_name
```


4. Execute the Pipeline

Launch Jupyter Notebook and run ```EDA.ipynb``` to clean the data and automatically push it to your PostgreSQL database.

Open ```sales_analytics_dashboard.pbix``` in Power BI, update the Data Source settings to point to your local PostgreSQL server, and hit Refresh.


## Dashboard Previews

Below are snapshots of the interactive Power BI dashboard, illustrating the end result of the data pipeline:


Customer Analysis Revenue![Customer Analysis Revenue](https://github.com/TGSK07/Customer_behaviour_analysis/blob/main/assets/page1.png)
Best-Worst Dashboard![Best-Worst Dashboard](https://github.com/TGSK07/Customer_behaviour_analysis/blob/main/assets/page2.png)

## Key Business Insights

Category Dominance: *Clothing* drives the vast majority of transaction volume and total revenue, though cross-selling strategies are required to boost *Footwear* and *Accessories*.

Demographic Disparities: The customer base skews heavily Male (68%). Expanding female-specific inventory and targeted marketing represents a massive growth opportunity.

Subscription Gaps: SQL cohort analysis identified a high volume of users who purchase *Weekly* or *Monthly* but lack an active subscription, representing an uncaptured recurring revenue stream.

Seasonal Stability: Total revenue maintains equitable distribution across all four seasons, providing highly predictable cash flow, with only minor optimizations needed during the Spring quarter.


📝 License

This project is licensed under the MIT License - see the LICENSE file for details.