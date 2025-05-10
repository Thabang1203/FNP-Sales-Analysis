## **Objective 1**
## **DATA SOURCE**
**I will download the dataset in github**
Here is the dataset link [download here](https://github.com/Ayushi0214/FNP---Excel-Project)
## **Objective 2**
# **Ferns & Petals Sales Analysis Dashboard - Project Summary**  

## **Objective**  
To analyze sales data of Ferns & Petals (an online gifting platform) and create an interactive Excel dashboard to derive actionable insights, such as revenue trends, delivery performance, and customer behavior.  

---

## **Tools & Techniques Used**  
- **Power Query Editor**: Data extraction, cleaning, and transformation.  
- **Power Pivot**: Data modeling (star schema) and DAX measures.  
- **Pivot Tables & Charts**: Data aggregation and visualization.  
- **Slicers & Timelines**: Interactive filtering.  
- **Correlation Analysis**: Statistical relationship between variables.  

---

## **Step-by-Step Execution**  

### **1. Data Extraction & Cleaning**  
- **Source**: Imported 3 CSV files (customers.csv, orders.csv, products.csv) using **Power Query Editor**.  
- **Transformations**:  
  - Converted contact numbers to text format.  
  - Extracted **month names**, **hour of order/delivery**, and **day names** from dates.  
  - Calculated **delivery time difference** (days) using:  
   excel
    = [Delivery Date] - [Order Date]  
   
  - Merged orders and products tables to fetch product prices using a **left outer join** on Product ID.  

---

### **2. Data Modeling (Power Pivot)**  
- Created a **star schema** with:  
  - **Fact Table**: orders (contains transactional data).  
  - **Dimension Tables**: customers and products.  
- Established relationships:  
  - orders[customer_id] → customers[customer_id] (1:many).  
  - orders[product_id] → products[product_id] (1:many).  
- Added **DAX measures**:  
  - **Total Revenue**:  
   excel
    Total Revenue = SUM(orders[Revenue])  
   
  - **Average Delivery Time**:  
   excel
    Avg Delivery Days = AVERAGE(orders[Delivery Time Difference])  
   
  - **Day of Order (using FORMAT)**:  
   excel
    Day Name = FORMAT(orders[Order Date], "dddd")  
   

---

### **3. Analysis & Dashboard Creation**  
#### **Key Questions Answered**  
1. **Total Revenue**:  
   - Used a pivot table to sum the Revenue column.  
   - **Formula**: =SUM(orders[Price] * orders[Quantity]).  

2. **Monthly Sales Trends**:  
   - Pivot table grouped by Month Name (sorted chronologically).  
   - **Insight**: Highest sales in **November** (Diwali/Rakshabandhan).  

3. **Top Products/Categories by Revenue**:  
   - Filtered top 5 products using:  
    excel
     Value Filters → Top 5 by Sum of Revenue  
    
   - **Top Category**: "Colors" (highest revenue).  

4. **Customer Spending Analysis**:  
   - Calculated **average order value**:  
    excel
     =AVERAGE(orders[Revenue])  
    
   - **Result**: R3,520 per order.  

5. **Order Quantity vs. Delivery Time (Correlation)**:  
   - Used CORREL() to analyze impact:  
    excel
     =CORREL(orders[Quantity], orders[Delivery Time Difference])  
    
   - **Result**: 0.347 (weak positive correlation).  

6. **Top Cities by Orders**:  
   - Pivot table with COUNT of Order ID grouped by city.  

---

### **4. Interactive Dashboard**  
- **Visualizations**:  
  - Bar charts (Revenue by occasion/category).  
  - Line chart (Monthly sales trend).  
  - Tables (Top products/cities).  
- **Interactivity**:  
  - Added **slicers** for Occasion and **timelines** for Order Date.  
  - Connected slicers to all pivot tables using **Report Connections**.  

---

### **5. Executive Summary**  
- **Key Findings**:  
  - **Peak Sales**: November (festive season).  
  - **Fastest Delivery**: Average **5.5 days**.  
  - **Popular Gifts**: Sweets, soft toys, and colors.  
- **Recommendations**:  
  - Boost marketing during festive months.  
  - Optimize delivery for high-quantity orders.  

---

## **GitHub Repository Contents**  
1. **Dataset**: customers.csv, orders.csv, products.csv.  
2. **Excel File**: Dashboard with Power Query steps.  
3. **Screenshot**: Dashboard preview.  
4. **PDF**: Problem statement and solutions.  

---
## **Objective 3**
DASHBOARD
[Ferns and Petals Sales Analysis]
![Screenshot 2025-05-10 094150](https://github.com/user-attachments/assets/6f89f5be-1434-4820-8852-9f46011bb0b3)

