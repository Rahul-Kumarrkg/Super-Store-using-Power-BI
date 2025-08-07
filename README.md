# 🛒 **Super Store Sales Analysis + Forecasting**

---

## ✅ Goals:

* Analyze historical sales, profit, and trends.
* **Forecast future sales/profit** using built-in Power BI tools.
* Provide business stakeholders with actionable, predictive insights.

---

## 🧾 1. Dataset Recap:

You’ll typically work with the **Sample Superstore Dataset**, which includes:

* `Order Date`, `Ship Date`,`Profit`, `Quantity`
* `Sum of Sales of Payment Method`,  `Sum of Sales by Region`,`Sum of Sales by Segment`
* `Category`, `Sub-Category`, `Ship Mode`
*  `Monthly Sales of YOY`, `Month;y Profit of YOY`

Dataset Link: https://www.kaggle.com/datasets/vivek468/superstore-dataset-final

---

## 🛠️ 2. Building the Report — Step by Step

### 🧹 Step 1: **Load & Clean the Data**

Use **Power Query Editor** to:

* Ensure `Order Date` is in Date format.
* Remove duplicates, nulls.
* Create a **Date Table** for accurate time intelligence.

> Tip: Use `CALENDAR(MIN(Orders[Order Date]), MAX(Orders[Order Date]))` to create a date table.

---

### 🔗 Step 2: **Model the Data**

* Establish relationships:

  * Orders ↔ Date Table (Order Date)
  * Orders ↔ Customers ↔ Regions, etc.

---

### 📊 Step 3: **Create Key Measures (DAX)**

Here are examples:

```DAX
Total Sales = SUM(Orders[Sales])
Total Profit = SUM(Orders[Profit])
```

Add **monthly or yearly aggregation** if needed:

```DAX
Sales by Month = CALCULATE([Total Sales], DATESMTD('Date'[Date]))
```

---

### 📈 Step 4: **Time Series Visualization for Forecast**

#### Create a **Line Chart**:

* X-axis: `Order Date` (Use hierarchy → Year, Month)
* Y-axis: `Total Sales` or `Total Profit`

#### Forecast:

1. Click on the Line Chart.
2. Go to the **Analytics pane** (right side).
3. Click on **“+ Add”** under **Forecast**.
4. Set forecast length:

   * Example: 5 days
5. Choose:

   * Confidence Interval (default is 95%)
   * Seasonality (Auto or manual, e.g., 15 days)
6. Click **Apply**.

#### Power BI will automatically:

* Analyze historical trends.
* Display a **forecast line** with **shaded confidence intervals**.

---

## 🧠 Business Insights You Can Present::

| Use Case          | Example                                                     |
| ----------------- | ----------------------------------------------------------- |
| Sales Forecast    | Predict next 15 days of total sales.                 |
| Profit Forecast   | See expected profit growth or decline.                      |
| Category Forecast | Forecast sales of key sub-categories like Chairs, Binders and Phones. |
| Region Forecast   | Predict sales for West,East,North or South region.                     |

---


## 🎨 6. Final Dashboard Layout Suggestion

### Page 1: Executive Overview

* KPI Cards: Total Sales, Profit, Forecasted Sales
* Line Chart with Forecast (12 months)
* Regional Sales Cards
* Category-wise Profit Bar

### Page 2: Forecast Analysis

* Forecasted Sales Trend (Line Chart)
* Forecast by States (Bar Chat)

---

## 📝 Bonus Tips:

* Use **What-If parameters** to simulate sales increases or price changes.
* Export forecasted values to Excel or Power BI Service.
* Use **Decomposition Tree** to analyze *why* forecast might change.

---

## 📌 Conclusion:

Forecasting in the Super Store Power BI project transforms your report from **descriptive to predictive** analytics. It enables businesses to **plan inventory, staffing, and promotions** based on future demand trends.
 


