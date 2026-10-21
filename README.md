# Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores customer purchasing patterns, spending behavior, product preferences, discounts, and subscription trends using Python, PostgreSQL, and Power BI.

## Overview

This project analyzes customer shopping data to identify meaningful business insights and support data-driven decision-making. The workflow covers data loading, exploratory data analysis (EDA), data cleaning, SQL-based analysis, interactive dashboard development, report preparation, and presentation creation using Gamma AI.

## Dataset

- **Dataset:** `customer_shopping_behavior.csv`
- **Records:** 3,900 purchases
- **Columns:** 18
- **Missing Values:** 37 values in the `Review Rating` column

The dataset includes information about:

- Customer demographics, including age, gender, and location
- Purchase details, product categories, and purchase amounts
- Discounts, promotional codes, and subscription status
- Shipping preferences, purchase frequency, and review ratings

## Tools & Technologies

- **Python:** Data analysis and preprocessing
- **Pandas & NumPy:** Data manipulation and cleaning
- **Matplotlib & Seaborn:** Exploratory data visualization
- **PostgreSQL:** Database storage and SQL-based analysis
- **SQLAlchemy:** Python–PostgreSQL integration
- **Power BI:** Interactive dashboard development
- **Gamma AI:** Presentation creation
- **Jupyter Notebook:** Executing Python analysis

## Project Workflow

### 1. Data Loading and Exploration

- Imported the dataset using Pandas.
- Examined data types, dataset structure, and summary statistics.
- Identified missing values and explored customer purchasing patterns.

### 2. Data Cleaning and Feature Engineering

- Handled missing review ratings using the median rating of each product category.
- Standardized column names using snake_case.
- Created customer age groups.
- Derived purchase frequency in days.
- Checked redundant columns and removed `promo_code_used` after comparing it with `discount_applied`.

### 3. PostgreSQL Integration

- Connected Python to PostgreSQL using SQLAlchemy.
- Loaded the cleaned DataFrame into the `customer` table.
- Used SQL queries to perform business-focused analysis.

Key SQL analyses included:

- Revenue comparison by gender
- High-spending customers who used discounts
- Top-rated products
- Average purchase amount by shipping type
- Subscriber versus non-subscriber spending
- Products with high discount dependency
- Customer segmentation into New, Returning, and Loyal
- Top-selling products by category
- Repeat buyers and subscription behavior
- Revenue contribution by age group

### 4. Power BI Dashboard

Built an interactive **Customer Behavior Dashboard** to visualize key metrics and shopping trends.

The dashboard includes:

- Total customers
- Average purchase amount
- Average review rating
- Customer distribution by subscription status
- Revenue and sales by product category
- Revenue and sales by age group
- Interactive filters for gender, category, subscription status, and shipping type

### 5. Report and Presentation

- Prepared a project report documenting the workflow, SQL analysis, findings, and business recommendations.
- Created a presentation using **Gamma AI** to communicate the project's objectives, methodology, visualizations, and key insights.

## Dashboard

The Power BI dashboard provides a consolidated view of customer behavior and business performance.

**Key metrics from the analysis:**

| Metric | Result |
|---|---:|
| Total Customers | 3,900 |
| Average Purchase Amount | $59.76 |
| Average Review Rating | 3.75 |
| Subscriber Share | Approximately 27% |
| Non-Subscriber Share | Approximately 73% |

*Note: These figures are based on the project report.*

## Results and Business Insights

The analysis identified several useful patterns:

- **Customer Segmentation:** Classified customers into New, Returning, and Loyal groups based on purchase history.
- **Subscription Analysis:** Compared spending and revenue between subscribers and non-subscribers.
- **Product Performance:** Identified highly rated products and best-selling products within categories.
- **Discount Analysis:** Highlighted products frequently purchased with discounts.
- **Shipping Analysis:** Compared average spending between Standard and Express shipping customers.
- **Age-Based Analysis:** Evaluated revenue contributions across customer age groups.

### Business Recommendations

- Promote exclusive subscription benefits to encourage customer sign-ups.
- Introduce loyalty programs to reward repeat customers.
- Review discount strategies to balance sales growth and profitability.
- Highlight top-rated and popular products in marketing campaigns.
- Target customer segments using age-group and purchasing insights.

## How to Run

### Prerequisites

Install Python, PostgreSQL, pgAdmin, Power BI Desktop, and Jupyter Notebook.

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
cd customer-shopping-behavior-analysis
```

### Step 2: Install Python Dependencies

```bash
pip install pandas numpy matplotlib seaborn sqlalchemy psycopg2-binary jupyter
```

### Step 3: Load the Dataset

Place `customer_shopping_behavior.csv` in the project directory and load it in Jupyter Notebook:

```python
import pandas as pd

df = pd.read_csv("customer_shopping_behavior.csv")

print(df.shape)
df.head()
```

### Step 4: Perform Data Cleaning and EDA

Open the project notebook and execute the cells for data exploration, missing-value handling, column standardization, feature engineering, and visualization.

### Step 5: Configure PostgreSQL

1. Open pgAdmin and create a database named `customer_behavior`.
2. Update the database connection credentials in your Python notebook.
3. Run the database integration code to load the cleaned DataFrame into the `customer` table.

Example connection:

```python
from sqlalchemy import create_engine, URL

url = URL.create(
    "postgresql+psycopg2",
    username="postgres",
    password="YOUR_PASSWORD",
    host="localhost",
    port=5432,
    database="customer_behavior"
)

engine = create_engine(url)

df.to_sql(
    "customer",
    engine,
    if_exists="replace",
    index=False
)
```

**Security note:** Replace `YOUR_PASSWORD` with your local PostgreSQL password. Do not commit database credentials to GitHub.

### Step 6: Execute SQL Queries

Connect to `customer_behavior` in pgAdmin and execute the project's SQL queries to reproduce the business analysis.

### Step 7: Open the Power BI Dashboard

Open the `.pbix` file in Power BI Desktop. If prompted, configure the PostgreSQL connection and refresh the data.

### Step 8: Review the Report and Presentation

Open the project report and Gamma AI presentation to explore the documented findings, visualizations, and recommendations.

## Project Deliverables

- Python notebook for EDA and data cleaning
- Cleaned dataset
- PostgreSQL SQL queries
- Interactive Power BI dashboard
- Project analysis report
- Gamma AI presentation

## Skills Demonstrated

**Data Analytics | Python | Pandas | Exploratory Data Analysis | Data Cleaning | SQL | PostgreSQL | Data Visualization | Power BI | Business Intelligence | Data Storytelling**

## Author

**Shivam Bhat**

Connect with me on [LinkedIn](YOUR_LINKEDIN_URL) | Explore my projects on [GitHub](YOUR_GITHUB_URL)
