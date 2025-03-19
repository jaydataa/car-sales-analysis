# Car Sales Analysis - Python & Power BI

##  Project Overview
This project analyses car sales data using **Python (Jupyter Notebook)** for data cleaning and **Power BI** for interactive visualisation. It provides insights into sales trends, customer demographics, dealer performance, and brand popularity.

##  Key Features
**Data Cleaning & Preprocessing:**
- Standardised date format (DD/MM/YYYY)
- Fixed inconsistent brand names
- Handled missing values (Annual Income)

**Exploratory Data Analysis (EDA):**
- Identified top-selling brands and models
- Analysed customer demographics and income distribution
- Uncovered seasonal sales trends

**Power BI Dashboard:**
- **Bar Chart:** Monthly sales trends
- **Line Chart:** Brand-wise sales over time
- **Heatmap:** Dealer performance analysis
- **Interactive Filters:** Gender, Income, Car Model, Dealer Name
- **Drillthroughs:** Click on a brand to see model-specific sales

## Files in This Repository
- `car_sales_analysis.ipynb` → Jupyter Notebook for data processing & EDA
- `car_sales_data.csv` → Raw dataset
- `Car_Sales_Dashboard.pbix` → Power BI interactive dashboard
- `ANALYSIS.md` → Detailed report on challenges & solutions
- `README.md` → Project overview & setup guide

## How to Run This Project
### **Python Analysis (Jupyter Notebook)**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/car-sales-analysis.git
   ```
2. Install dependencies:
   ```bash
   pip install pandas matplotlib seaborn
   ```
3. Open the Jupyter Notebook and run the analysis:
   ```bash
   jupyter notebook car_sales_analysis.ipynb
   ```

### **Power BI Dashboard**
1. Open **Power BI Desktop**
2. Load the file `Car_Sales_Dashboard.pbix`
3. Interact with the dashboard to explore insights
