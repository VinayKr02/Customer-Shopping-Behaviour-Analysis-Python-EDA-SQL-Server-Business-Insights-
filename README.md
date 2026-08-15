# Customer-Shopping-Behaviour-Analysis-Python-EDA-SQL-Server-Business-Insights-
End-to-end analysis of a 3,900-record retail customer transaction dataset, combining Python for data cleaning and exploratory analysis with SQL Server for structured business-question querying.

**📌 Objective**

Explore customer shopping behavior to answer questions a retail business would care about: who is spending and how much, whether discounts and subscriptions correlate with higher spend, which products and categories perform best, and how customers can be segmented by purchase history.

**🧹 Data Cleaning & Preparation**
Profiled the raw data: data types, summary statistics, column-length checks
Standardized column names (lowercase, stripped whitespace, underscores)
Imputed 37 missing review_rating values using the category-wise median
Renamed purchase_amount_(usd) → purchase_amount
Detected that discount_applied and promo_code_used held identical information and dropped the redundant column

**🛠️ Feature Engineering**
age_group: quartile-based bins (Young / Adult / Middle-Aged / Senior) via pd.qcut
frequency_of_purchases_days: numeric day-interval mapping from purchase-frequency labels (e.g., Weekly → 7, Monthly → 30)
📊 Exploratory Data Analysis

**Visualizations built with Matplotlib/Seaborn:**

Customer distribution by gender (2,652 male vs. 1,248 female)
Top 10 most purchased items
Distribution of purchase amount
Purchase amount by category (boxplot)
Average purchase amount by category
Product category distribution by age group
Purchase frequency distribution

**🗄️ SQL Server Integration**
Connected the notebook to SQL Server using SQLAlchemy + pyodbc (ODBC Driver 17 for SQL Server)
Loaded the cleaned dataset into a customer_purchase table via to_sql()
Queried table metadata (sys.tables, INFORMATION_SCHEMA.TABLES) to confirm the load

**🔎 SQL Business Analysis**

**Customer_Shopping_Behaviour_Analysis.sql answers:**

Total revenue by gender
Customers who used a discount but still spent above average
Top 5 products by average review rating
Standard vs. Express shipping — average purchase amount comparison
Subscriber vs. non-subscriber — count, total revenue, average spend
Top 5 products by discount-usage rate
Customer segmentation into New / Returning / Loyal (CTE)
Top 3 best-selling products within each category (ROW_NUMBER() window function)
Repeat buyers (5+ previous purchases) vs. subscription status
Revenue contribution by age group
🧰 Tools & Technologies

Python (Pandas, NumPy, Matplotlib, Seaborn) · Jupyter Notebook · Microsoft SQL Server (T-SQL) · SQLAlchemy · pyodbc
