# solar-Vision-Power-Bi

# ☀️ Solar Vision Executive Dashboard — Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

---

## 📌 Project Overview

**Solar Vision Executive Dashboard** is an interactive Power BI dashboard built to provide end-to-end visibility into solar supply chain & logistics operations.

It enables executives and decision-makers to monitor **Supplier performance, Inventory levels, Shipment tracking, and Customer delivery metrics** — all in one unified dark-themed interface with real-time filtering by country.

---

## 🖼️ Dashboard Preview
https://github.com/khush3521/solar-Vision-Power-Bi/blob/main/Solar_ss.png


---

## 📊 Key KPI Metrics

| Metric | Value |
|---|---|
| 💰 Gross Revenue | 186.86M |
| 📈 Total Revenue | 176.95M |
| 💵 Total Profit | 48.56M |
| 📉 Profit Margin | 27.44% |
| ✅ Perfect Order Rate | 75% |
| 🚚 Total Shipments | 8K |
| 📦 Total Shipment Quantity | 3M |
| 🏭 Inventory Value | 160K |
| 🛒 Quantity (Units) | 129K |
| 📬 Total Delivered Quantity | 187K |

---

## 🔍 Dashboard Modules

### 1. 🚢 Supplier Module
- Displays **Average Lead Time** by supplier
- Top suppliers: BOE Technology, Samsung, Sony Semi, Taiwan Semi, SK Hynix
- All top 5 suppliers maintain an avg. lead time of **12 days**

### 2. 🏠 Inventory Module
- Shows **Inventory Value** by product
- Galaxy series dominates with highest inventory (25K at top)
- Visual: Horizontal bar chart sorted by inventory value

### 3. 🚛 Shipment Module
- Tracks **Total Profit by Product**
- Galaxy series leads with 9.2M at top
- Neo QL and OLED series also contribute significantly

### 4. 👤 Customer Module
- Monitors **Total Profit by Retailer/Customer**
- Top customers: Amazon (10.1M), Flipkart (10.1M), Best Buy (10.0M), MediaMarkt (9.6M), Samsung (8.9M)

---

## 🧮 DAX Measures — All 10 Queries

### 1️⃣ Gross Revenue
```dax
Gross_Revenue = SUM(Sales[Gross_Revenue])
```

### 2️⃣ Total Revenue
```dax
Total_Revenue = SUM(Sales[Total_Revenue])
```

### 3️⃣ Total Profit
```dax
Total_Profit = [Gross_Revenue] - SUM(Sales[Total_Cost])
```

### 4️⃣ Profit Margin %
```dax
Profit_Margin% = 
DIVIDE([Total_Profit], [Gross_Revenue], 0) * 100
```

### 5️⃣ Perfect Order Rate
```dax
Perfect_Order_Rate = 
DIVIDE(
    COUNTROWS(FILTER(Orders, Orders[Status] = "Perfect")),
    COUNTROWS(Orders),
    0
) * 100
```

### 6️⃣ Total Shipment Quantity
```dax
Total_Shipment_Qty = SUM(Shipment[Shipment_Quantity])
```

### 7️⃣ Total Delivered Quantity
```dax
Total_Delivered_Qty = 
CALCULATE(
    SUM(Shipment[Quantity]),
    Shipment[Status] = "Delivered"
)
```

### 8️⃣ Inventory Value
```dax
Inventory_Value = 
SUMX(
    Inventory,
    Inventory[Quantity] * Inventory[Unit_Price]
)
```

### 9️⃣ Average Lead Time by Supplier
```dax
Avg_Lead_Time = 
AVERAGEX(
    Supplier,
    Supplier[Lead_Time_Days]
)
```

### 🔟 Total Profit by Customer
```dax
Total_Profit_By_Customer = 
CALCULATE(
    [Total_Profit],
    ALLEXCEPT(Customer, Customer[Customer_Name])
)
```

---

## 🛠️ Tools & Technologies Used

| Tool | Purpose |
|---|---|
| Microsoft Power BI Desktop | Dashboard development & visualization |
| DAX (Data Analysis Expressions) | Custom KPI measures & calculations |
| Power Query (M Language) | Data cleaning & transformation |
| Data Modeling | Table relationships & schema design |

---

## 📁 Project Structure

```
Solar-Vision-Dashboard/
│
├── 📊 SolarVision_Dashboard.pbix     # Main Power BI file
├── 📁 Data/
│   ├── Sales_Data.xlsx
│   ├── Supplier_Data.xlsx
│   ├── Inventory_Data.xlsx
│   ├── Shipment_Data.xlsx
│   └── Customer_Data.xlsx
├── 📁 Screenshots/
│   └── dashboard_preview.png
└── 📄 README.md
```

---

## ✨ Dashboard Features

- 🌍 **Country-level slicer** for dynamic regional filtering
- 📌 **KPI Cards** for quick executive-level insights
- 📊 **Horizontal Bar Charts** for top-N product & supplier comparisons
- 🌑 **Dark Navy Theme** for professional executive readability
- 🔗 **4 Navigation Modules** — Supplier, Inventory, Shipment, Customer

---



## 📈 Insights & Findings

- 📦 **Galaxy series products** dominate both inventory and shipment volume
- 🏬 **Amazon and Flipkart** are tied as top customers (10.1M each)
- 🏭 **Top 5 suppliers** all maintain consistent 12-day average lead times
- 💹 A **27.44% profit margin** reflects strong operational efficiency
- ✅ **75% perfect order rate** shows room to improve last-mile delivery

---

## 🔮 Future Improvements

- [ ] Add **Month-over-Month (MoM)** trend analysis
- [ ] Integrate **forecasting visuals** using Power BI AI features
- [ ] Add **drill-through pages** for each supplier and customer
- [ ] Build a **mobile-optimized layout**
- [ ] Connect **live data source** via Power BI Service & Gateway

---

## 👨‍💻 Author

**[Khush Panchal]**
- 🌐 LinkedIn: www.linkedin.com/in/khush-panchal-96b557352
- 💻 GitHub: 


---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, modify, and share with attribution.

---

⭐ **If you found this project helpful, please give it a star!** ⭐
