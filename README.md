# Swiggy Sales Analysis | Power BI Project

## Project Overview
This project analyzes Swiggy order level data to understand sales trends, customer behavior, and restaurant performance.
The project was built completely from scratch, starting from raw transactional data and ending with a fully optimized Power BI dashboard.

The main focus of this project is data understanding, transformation, and correct modeling rather than only creating visuals.

---

## Dashboard Overview
Add the dashboard overview image below.

![Dashboard Overview](<img width="1159" height="645" alt="Screenshot 2026-01-06 185420" src="https://github.com/user-attachments/assets/536f84e1-2631-494a-875f-c988a9cc79a1" />
)

---

## Dataset Description
The dataset contains transactional and master data related to food orders on Swiggy.

### Tables Used
- Orders: Order level transactional data
- Users: Customer demographic information
- Restaurants: Restaurant details and location
- Menu: Food items and pricing
- Food: Food category and type information

---

## Data Preparation and EDA
The raw Orders data was initially available in long format, where sales quantity and sales amount were stored in separate rows using Type and Value columns.

### Key Challenges
- Inflated row count due to long format structure
- Ambiguity caused by a generic Value column
- Need for an analytics ready fact table

### Transformations Performed
- Converted long format data into wide format by creating:
  - Sales_QTY
  - Sales_amount
- Corrected data types for all columns
- Created derived columns:
  - Year
  - Month Number
  - Month Name
  - Weekday or Weekend
- Removed redundant and unused columns

All transformations were validated using EDA in Jupyter Notebook before final implementation in Power BI.

---

## Data Modeling
A Star Schema was implemented for better performance and clarity.

### Fact Table
- Orders

### Dimension Tables
- Users
- Restaurants
- Menu
- Food

### Modeling Decisions
- City attribute kept only in Restaurants table
- Relationships used instead of merging tables
- One to many relationships with single direction filtering

---

## Measures and Analysis
Key metrics were implemented using DAX:

- Total Sales
- Total Quantity Sold
- Total Orders
- Dynamic Top N Restaurants and Cities
- Weekday vs Weekend analysis

A disconnected Rank Table was created to enable dynamic Top N analysis without hard coding values in DAX.

---

## Business Insights
This dashboard helps answer key business questions such as:
- Which cities generate the highest revenue
- Which restaurants contribute the most to total sales
- How demand differs on weekdays versus weekends
- Monthly and yearly sales trends

---

## Tools and Technologies
- Power BI for data modeling, DAX, and visualization
- Power Query for data transformation
- Python with Jupyter Notebook for EDA
- Excel and CSV files as data sources

---

## Key Learnings
- Importance of data shape and structure
- Long format versus wide format data handling
- Correct fact and dimension table design
- Avoiding redundancy using relationships
- Controlling aggregation logic through DAX measures

---

## How to Use
1. Clone the repository
2. Open the Power BI PBIX file
3. Refresh the data sources if required
4. Explore the dashboard using slicers and filters

---

## Note
This project was rebuilt from scratch for learning and interview preparation.
All transformations and modeling decisions are fully understood and explainable.
