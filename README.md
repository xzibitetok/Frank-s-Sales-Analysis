# 📊 Frank Sales Analysis — Excel First, then Power BI
![Excel](https://img.shields.io/badge/Excel-Analysis-217346)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811)
![Status](https://img.shields.io/badge/Status-Portfolio%20Ready-brightgreen)

**One-liner (use as GitHub description):**  
End-to-end sales analysis using **Excel for data preparation & pivot dashboards** and **Power BI for interactive reporting**.

---

## 🧭 Table of Contents
1. [Project Summary](#-project-summary)  
2. [Files in This Repository](#-files-in-this-repository)  
3. [Excel Analysis (Start → Finish)](#-excel-analysis-start--finish)  
4. [Power BI Visualization](#-power-bi-visualization)  
5. [Key Insights (Examples)](#-key-insights-examples)  
6. [How to Run](#-how-to-run)
7. [Author](#-author)


---

## 🧠 Project Summary
This project transforms raw sales transactions into **clear, decision-ready insights**.  
- **Excel** is used for cleaning, exploring, and building **pivot-based dashboards**.  
- **Power BI** extends the analysis into an **interactive, shareable report** with KPIs, trends, and drill-downs.

---

## 📁 Files in This Repository
| Path/File | Purpose |
|---|---|
| `data/Xzibit Sales Spreadsheet.xlsx` | **Excel source** used for cleaning, pivots, and (optionally) an Excel dashboard |
| `powerbi/xzibit report.pbix` | **Power BI** report built on the Excel data |
| `images/` | Screenshots used in this README (placeholders listed below) |
| `README.md` | This documentation |

> ℹ️ If your `.pbix` is large, consider **Git LFS** so GitHub can store it smoothly.

---

## ✅ Excel Analysis (Start → Finish)
**File:** `data/Xzibit Sales Spreadsheet.xlsx`  
**Sheets expected:** `Orders`, `People`, `Returns`  

### 1) Data Understanding
- **Orders** (fact): Order details, dates, customer, segment, region, product, sales, discount, profit, etc.  
- **People** (dim): Region → Manager mapping.  
- **Returns** (dim): Returned orders by `Order ID`.

📸 **Raw Data Sample (Excel)**  
![Order A](https://github.com/xzibitetok/Frank-s-Sales-Analysis/blob/main/Order%20A.png)
![Order B](https://github.com/xzibitetok/Frank-s-Sales-Analysis/blob/main/Order%20B.png)
![People](https://github.com/xzibitetok/Frank-s-Sales-Analysis/blob/main/People.png)
![Returns](https://github.com/xzibitetok/Frank-s-Sales-Analysis/blob/main/Returns.png)
---

### 2) Cleaning & Preparation (Excel)
- Remove duplicates (use `Row ID` as key).
- Ensure correct data types: dates, numbers, text.
- Handle missing values (e.g., `Postal Code` → leave blank or use `N/A`).
- Optional helper fields (examples):
  - **Order Year** = `YEAR([Order Date])`
  - **Order Month** = `TEXT([Order Date], "YYYY-MM")`
  - **Profit Margin** = `Profit / Sales`

---

### 3) Pivot Tables (Excel)
Create these pivots on a dedicated sheet (e.g., `PIVOT TABLES`):
- **Sales by Region** (Rows: Region; Values: Sum of Sales)
- **Sales by Category & Sub-Category** (Rows: Category → Sub-Category; Values: Sum of Sales)
- **Profit by Segment** (Rows: Segment; Values: Sum of Profit)
- **Monthly Sales Trend** (Rows: Year/Month; Values: Sum of Sales)
- **Returns Impact** (Use a helper or `Returns` join indicator to compare Returned vs Not Returned)

📸 **Pivot Summary (Excel)**  
![Table View A](https://github.com/xzibitetok/Frank-s-Sales-Analysis/blob/main/Table%20View%20A.png)

---

## 📊 Power BI Visualization
**File:** [📥 Download Frank Sales Report.pbix](https://github.com/xzibitetok/Frank-s-Sales-Analysis/blob/main/Frank%20Sales%20report.pbix?raw=true)


### Model & Relationships
- **Orders** (fact) connected to **People** by `Region`
- **Orders** connected to **Returns** by `Order ID`

### Core Measures (Examples)
- **Total Sales** = `SUM(Orders[Sales])`  
- **Total Profit** = `SUM(Orders[Profit])`  
- **Total Quantity** = `SUM(Orders[Quantity])`  
- **Profit Margin** = `DIVIDE([Total Profit], [Total Sales])`  
- **Return Rate** = `DIVIDE(DISTINCTCOUNT(Returns[Order ID]), DISTINCTCOUNT(Orders[Order ID]))`

### Suggested Visuals
- **KPIs:** Total Sales, Total Profit, Profit Margin, Return Rate  
- **Trends:** Sales by Month (Line/Area)  
- **Breakdowns:** Sales by Category/Sub-Category (Bar), Profit by Segment (Donut), Sales by Region (Map or Bar)  
- **Filters/Slicers:** Region, Segment, Category, Year

📸 **Power BI Dashboard**  
![Report View](https://github.com/xzibitetok/Frank-s-Sales-Analysis/blob/main/Report%20View.png)

---

## 🔍 Key Insights (Examples)
> Replace with your actual findings after reviewing the pivots/visuals.

| Theme | Example Insight |
|---|---|
| 🏆 Top Region | West leads revenue; Central shows strongest recent growth. |
| 📂 Category | Technology drives profit; Office Supplies leads volume. |
| 📈 Trend | Q4 surge in sales with improved margins vs Q2. |
| 🚚 Returns | Return rate concentrated in Consumer segment; monitor discounts. |

---

## 🚀 How to Run
1. **Clone** the repo:
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
2. ### **Open Excel File**  
- Navigate to **`Xzibit Sales Spreadsheet.xlsx`**  
- Explore the sheets:  
  - **Orders** – Raw sales data  
  - **Pivot Tables** – Analytical summaries  
  - **Dashboard** – Interactive visuals  

3. ### **Open Power BI File**  
- Open **`Xzibit Report.pbix`** in **Power BI Desktop**  
- Interact with slicers and charts for deeper insights  

---

## 📌 Author  
**Ubong Etok**  
A data analyst passionate about transforming raw data into actionable insights using **Excel** and **Power BI**.  

🔗 **Connect with me:**  
- [LinkedIn](https://www.linkedin.com/in/ubong-etok-56b4a0170)  
- [GitHub](https://github.com/xzibitetok)  
- [Email](mailto:ubyetok@gmail.com)  

---

## 🎯 Purpose  
This project demonstrates:  
✔ End-to-end analytics workflow (**Excel → Power BI**)  
✔ Data cleaning, transformation, and visualization skills  
✔ A portfolio-ready business intelligence project  

> **If you're a recruiter, collaborator, or data enthusiast, feel free to reach out!**  
