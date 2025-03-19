# Car Sales Data Analysis - Project Overview

## Project Summary
This project analyses car sales data using **Python (Jupyter Notebook) and Power BI**. The goal is to uncover trends in car sales based on customer demographics, dealer performance, and car brand preferences.

### **Technologies Used:**
- **Python (Pandas, Matplotlib, Seaborn)** → Data Cleaning, EDA, and Statistical Analysis
- **Power BI** → Interactive Dashboard for Visualising Insights
- **GitHub** → Repository for storing project files and documentation

---
## Data Cleaning Process
**Dataset Columns:**
- Car ID, Date, Customer Name, Gender, Annual Income, Dealer Name, Car Brand, Model, Engine, Transmission

### **Challenges Faced & Solutions**

### **Issue 1: Date Format (American MM/DD/YYYY Format)**
**Problem:** The dates were formatted incorrectly, leading to errors in time-based analysis.

**Solution:** Used Python to convert the format to **DD/MM/YYYY**.
```python
# Convert date column to correct format
df['Date'] = pd.to_datetime(df['Date'], format='%m/%d/%Y')
df['Date'] = df['Date'].dt.strftime('%d/%m/%Y')
```

---

### **Issue 2: Inconsistent Car Brand Names**
**Problem:** Some brands had multiple spellings (e.g., "Mercedes-Benz" vs. "Mercedes").

**Solution:** Standardized brand names using Python.
```python
df['Company'] = df['Company'].replace({'Mercedes-Benz': 'Mercedes', 'BMW Group': 'BMW'})
```

---

### **Issue 3: Missing Annual Income Data**
**Problem:** Some customers had missing annual income data.

**Solution:** Filled missing values with the median income of customers who bought the same car brand.
```python
# Fill missing annual income with brand-wise median
df['Annual Income'] = df.groupby('Company')['Annual Income'].transform(lambda x: x.fillna(x.median()))
```

---
## Exploratory Data Analysis (EDA)
### **Insights Found:**
**Which brands perform best in sales?**
- Toyota and Ford had the highest sales volume.
- Luxury brands like BMW & Mercedes had fewer but higher-value sales.

**What is the income distribution of car buyers?**
- Most buyers earn between **$50,000 - $100,000** annually.
- Buyers of luxury cars generally have an income of **$150,000+**.

**Seasonal Sales Trends**
- Sales peak in **June and December**, possibly due to mid-year promotions and end-of-year discounts.
- February had the lowest sales.

---
## Power BI Dashboard - Features
- **Bar Chart:** Monthly car sales trends
- **Line Chart:** Brand-wise sales over time
- **Heatmap:** Dealer-wise sales distribution
- **Interactive Filters:** Gender, Income, Car Model, Dealer Name
- **Drill-throughs:** Click a brand to see model-specific sales

---
## Challenges in Power BI & Solutions

### **Issue 1: Conditional Formatting for Brand Colors**
**Problem:** The car brand colors in the bar chart did not match the line chart.

**Solution:** Created a **DAX measure** to assign colors dynamically:
```DAX
CarBrand_VisualColor =
SWITCH(
    SELECTEDVALUE(Company),
    "Toyota", "#FF5733",
    "Ford", "#4285F4",
    "BMW", "#F4B400",
    "Mercedes", "#34A853",
    "Tesla", "#990099"
)
```
Applied this measure to **Data Colors → Conditional Formatting**.

---

### **Issue 2: Missing Search Feature**
**Problem:** Users could not search for a specific car model.

**Solution:** Added a **Text Filter** visual and linked it to the dataset.

---
##Conclusion & Next Steps
**Project Takeaways:**
- Cleaning inconsistent data is crucial for analysis.
- Power BI drill-through and filtering improve user experience.
- Python + Power BI is a great combination for data analytics.

**Next Steps:**
- Implement **predictive analytics** for sales forecasting.
- Deploy an interactive **web-based dashboard**.
