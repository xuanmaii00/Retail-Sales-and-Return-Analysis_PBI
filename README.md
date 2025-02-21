# Retail Sales and Returns Analysis_Power BI

## 📑 Table of Contents
- 📌 [Background & Overview](#background--overview)
- 📂 [Dataset Description & Data Structure](#dataset-description--data-structure)
- 🧠 [Design Thinking Process](#design-thinking-process)
- 📊 [Key Insights & Visualizations](#key-insights--visualizations)
- 🔎 [Final Conclusion & Recommendations](#final-conclusion--recommendations)

---

## 📌 Background & Overview

### **Objective**
This Power BI project for **Global Superstore Sales**, a multinational retail company, analyzes retail sales and returns to provide insights into sales performance, return trends, and customer purchasing behavior. The goal is to help businesses optimize inventory management, reduce return rates, and improve overall sales strategies.

### **👤 Who is this project for?**
- ✔️ Data analysts & business analysts  
- ✔️ Retail managers & inventory controllers  
- ✔️ Decision-makers & stakeholders  

### **❓ Business Questions**
- ✔️ What are the best-selling products and seasonal trends?  
- ✔️ What is the return rate for each product category?  
- ✔️ How can we optimize inventory management based on sales and return data?  
- ✔️ How do different customer segments contribute to total revenue and returns?  

### **🎯 Project Outcome**
- ✔️ **Sales Trends:** Identified peak sales periods and top-performing products.  
- ✔️ **Return Analysis:** Found that Category X has the highest return rate due to defective items.  
- ✔️ **Customer Behavior:** Repeat customers contribute 60% of revenue, while new customers have a higher return rate.  

---

## 📂 Dataset Description & Data Structure

### **📌 Data Source**
- **Source:** Internal company database  
- **Size:** 50,000+ transactions  
- **Format:** `.csv`  

### **📊 Data Structure & Relationships**

#### **1️⃣ Original Tables**
- ✔️**Orders**: Contains details for each transaction, like order dates, product info, sales, and profit.
- ✔️ **People**: Includes information on sales representatives in different regions.  
- ✔️ **Returns**: : Tracks returned transactions with product and region details.Orders: Sales Transactions 

#### **2️⃣ Table Schema & Data Snapshot**  
After cleaning, trasforming and data modeling, the final schema follows a **star schema** structure with the following tables:
- ✔️ **Fact_Orders** (Sales Transactions)  
- ✔️ **Dim_Customer** (Customer Information)  
- ✔️ **Dim_Returns** (Returns Data)  
- ✔️ **Dim_Seller** (Sales Representative Details)  
- ✔️ **Dim_Date** (Date Dimension Table)
##### **Fact_Orders Table (Sales Transactions)**
| Column Name  | Data Type | Description |
|-------------|----------|-------------|
| Category    | TEXT     | Product category |
| City        | TEXT     | City of the order |
| Customer_ID | INT      | Foreign key linking to Dim_Customer |
| Order_Date  | DATE     | Date of order |
| Order_ID    | INT      | Unique identifier for each order |
| Product_ID  | INT      | Foreign key linking to product details |
| Sales       | FLOAT    | Revenue from the order |
| Profit      | FLOAT    | Profit from the order |
| Quantity    | INT      | Number of units sold |

##### **Dim_Customer Table (Customer Information)**
| Column Name     | Data Type | Description |
|---------------|----------|-------------|
| Customer_ID  | INT      | Unique identifier for each customer |
| Segment      | TEXT     | Customer segment |
| Customer_Name | TEXT   | Full name of the customer |

##### **Dim_Returns Table (Returns Data)**
| Column Name  | Data Type | Description |
|-------------|----------|-------------|
| Order_ID    | INT      | Unique identifier for each returned order |
| Returned    | TEXT     | Indicates whether an order was returned (Yes) |

##### **Dim_Seller Table (Sales Representatives)**
| Column Name  | Data Type | Description |
|-------------|----------|-------------|
| Region      | TEXT     | Sales region |
| SalesPerson | TEXT     | Name of the salesperson responsible for the order |

##### **Dim_Date Table (Date Dimension)**
| Column Name      | Data Type | Description |
|-----------------|----------|-------------|
| Date           | DATE     | The date field |
| Year           | INT      | Extracted year |
| Month          | TEXT     | Month name |
| Quarter        | TEXT     | Quarter of the year (e.g., Q1, Q2) |
| Month Number   | INT      | Numeric representation of the month |
| Year-Month     | TEXT     | Year and month combined |
| Day            | INT      | Day of the month |
| Weekday        | TEXT     | Name of the weekday |
| Weekday Number | INT      | Numeric representation of the weekday |
| Is Weekend     | BOOLEAN  | Indicates if the date falls on a weekend |
| Week Number    | INT      | Week of the year |
| Day of Year    | INT      | Day number within the year |

### **3️⃣ Data Relationships (Star Schema)**
✔️ **Fact_Orders** ↔ **Dim_Customer** (One-to-Many via Customer_ID)  
✔️ **Fact_Orders** ↔ **Dim_Returns** (One-to-One via Order_ID)  
✔️ **Fact_Orders** ↔ **Dim_Date** (One-to-Many via Order_Date)  
✔️ **Fact_Orders** ↔ **Dim_Seller** (One-to-Many via Region)  

👉 ![Image](https://github.com/user-attachments/assets/34edcfbe-5b0a-4d02-b5f3-8c08c4c665a7)
---

## 🧠 Design Thinking Process

### **1️⃣ Empathize**  
Understand the pain points in sales and return analysis.  

### **2️⃣ Define Point of View**  
Define the key challenges, such as identifying return patterns and high-demand products.  

### **3️⃣ Ideate**  
Brainstorm potential solutions using Power BI dashboards.  

### **4️⃣ Prototype & Review**  
Build initial dashboards, review, and refine insights.  

👉 **Include a screenshot of the Design Thinking framework.**

### **⚒️ Main Process**  
- ✔️ **Data Cleaning & Preprocessing** (Handled missing data, inconsistencies)  
- ✔️ **Exploratory Data Analysis (EDA)** (Identified key trends in sales & returns)  
- ✔️ **Power BI Dashboard Creation**  

👉 **Include SQL queries or Power BI transformations used in data cleaning.**  

---

## 📊 Key Insights & Visualizations

### **🔍 Dashboard Preview**

#### **1️⃣ Sales Performance Overview**
👉 **Insert Power BI dashboard screenshot.**  
- ✔️ **Observation:** Sales peak during holiday seasons.  
- ✔️ **Recommendation:** Increase stock and promotional activities in Q4.  

#### **2️⃣ Return Analysis**
👉 **Insert Power BI dashboard screenshot.**  
- ✔️ **Observation:** Electronics have the highest return rate.  
- ✔️ **Recommendation:** Improve quality control and customer return policies.  

#### **3️⃣ Customer Segmentation**
👉 **Insert Power BI dashboard screenshot.**  
- ✔️ **Observation:** Repeat customers generate 60% of revenue.  
- ✔️ **Recommendation:** Implement a loyalty program to increase retention.  

---

## 🔎 Final Conclusion & Recommendations

### 📌 **Key Takeaways**
- ✔️ **Increase stock for high-demand periods to prevent stockouts.**  
- ✔️ **Implement stricter quality control for high-return products.**  
- ✔️ **Launch targeted promotions for high-value customers to improve retention.**  

This project provides actionable insights for optimizing sales and return processes, improving customer retention, and enhancing overall retail profitability. 🚀
 



### 1. Sales Overview
   #### a, Parameter: Segment
![Image](https://github.com/user-attachments/assets/34f61f0e-c026-468b-8cca-522b455ce68f)
   #### b, Parameter: Category
![Image](https://github.com/user-attachments/assets/1f651d11-4363-4665-8ea6-9c2d04c48c72)
   #### c, Parameter: Sub-Category
![Image](https://github.com/user-attachments/assets/8c65aeba-21e6-45ac-bf88-b3c2d4525f6b)
   #### d, Parameter: Market
![Image](https://github.com/user-attachments/assets/ffb3a21a-fb27-4904-ac86-86c00c90f996)
   #### e, Parameter: Region
![Image](https://github.com/user-attachments/assets/5857e205-89e8-40fc-9b59-d5a06c8fe27f)
### 2. Returns Overview
   #### a, Metric: Return Orders
![Image](https://github.com/user-attachments/assets/613a683e-0473-4791-bb1a-989dbefc8df4)
   #### b, Metric: Return Revenue
![Image](https://github.com/user-attachments/assets/2d91b36c-4713-4ae0-86b8-4a5732b365e6)
   #### c, Metric: Return Profit
![Image](https://github.com/user-attachments/assets/a36bb28e-ace3-451c-89fb-2c8a8ab99c85)
   #### d, Metric: Return Rate
![Image](https://github.com/user-attachments/assets/168efc0b-d8c5-4a28-8fb8-e7f308643c09)
### 3. Market Analysis
![Image](https://github.com/user-attachments/assets/d7e452ed-ff6a-48b6-a6d6-5191f5fb7361)
### 4. Product Analysis
![Image](https://github.com/user-attachments/assets/1b56850a-1bee-4530-807a-e61cf207dea6)

## III/ Insights and Recommendations
- In general, net profit margin of this year(2014) is relatively low comparing to the same period of last year(2013) ( from 1-2%)
- While the net profit margin of Home Office Customers are high(11.71%), they only contribute 20.8% to the company success profit -> need to raise the consumption of this group
- Table is the product line that has negative net profit margin(-12.3%), although it contribute to the revenue but the profit is negative -> stop this product line or figure out what are the cost led to negative profit( operating cost, depreciation cost,...)
- Paper is the product line with significant NPM(26.29%- more than twice the average NPM) -> invest in marketing, attract more purchase for this product line, choose this as the strategic product
- Try to increase the NPM by reducing COGS (find new supplier, do backward integration,..)
- Focus on the Consumer group as the Target Customer Segment, tailor the products and or buying policies for the group
- Some new Quantity Discount policies to attract more Corporate and Home Office consumers, also to avoid the Returns of large Cart Value Orders
- Investigate the reasons behind the high return rate from APAC and North Asia, develop some policies to restrain Returns in such areas














