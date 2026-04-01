# 🏨 Hotel Revenue Analytics Dashboard
### Infosys Springboard Virtual Internship 6.0

---

## 📌 Project Overview

This project was developed as part of the **Infosys Springboard Virtual Internship 6.0** program. The objective is to build a comprehensive **Hotel Revenue Analytics Dashboard** using Power BI, covering data generation, data modeling, KPI analysis, customer segmentation, and RFM (Recency, Frequency, Monetary) analysis for a hotel chain operating across multiple branches in India.

The dataset was self-generated to simulate real-world hotel operations across 15 branches and 4,000+ customers, covering booking data from 2023 to 2026.

---

## 👤 Submitted By
**Ashish Chauhan**
Infosys Springboard Virtual Internship 6.0

---

## 🗂️ Project Structure

```
Hotel-Revenue-Analytics/
│
├── Module_1/       → Data Generation, Data Modeling & Star Schema
├── Module_2/       → KPI Calculations, Master Data & Dashboard Page 1
├── Module_3/       → Guest Segmentation & RFM Analysis
├── Module_4/       → Forecasting & Cancellation Trend Analysis
├── Module_5/       → Dynamic Pricing & Ancillary Revenue Analysis
└── README.md
```

---

## 📦 Dataset Description

The dataset was self-generated and consists of **6 interlinked tables** structured as a **Star Schema** in Power BI:

| Table | Rows × Columns | Description |
|-------|----------------|-------------|
| Customer | 4,000 × 22 | Guest demographics, nationality, account status |
| Branch | 15 × 25 | Hotel branch details across India (Taj, ITC, etc.) |
| Date | 1,278 × 12 | Full date dimension with fiscal, holiday & weekend flags |
| Bookings | 25,000 × 19 | Core fact table — booking transactions |
| Rooms | 13 × 11 | Room types, amenities, pricing per night |
| Duration Details | 25,000 × 7 | Derived table with stay duration and revenue |

---

## 🔧 Modules Breakdown

### Module 1 — Data Generation & Data Modeling
- Generated 5 core tables: **Customer, Branch, Date, Booking, Rooms**
- Created calculated columns: Stay Type, Branch Name, and more
- Loaded all tables into **Power BI** using Get Data
- Built a **Star Schema** with Bookings as the central Fact table surrounded by dimension tables
- Applied data cleaning techniques in Excel (data type corrections, formatting)
- Used **Transform Data** in Power BI for further data quality improvements

### Module 2 — KPI Analysis & Dashboard Page 1
- Created **Duration Details** table (25,000 × 7) using booking check-in/check-out data
- Used **Group By** to create Rooms Booked aggregations
- Built **Yearly and Monthly Date Pivot Tables** for time-series analysis
- Created **Master Data Table** with key calculated columns:
  - **Occupancy %** — percentage of rooms filled
  - **ADR** (Average Daily Rate) — average price earned per room per night
  - **RevPAR** (Revenue Per Available Room) — combined pricing and occupancy efficiency metric
- Created **Booking Details Table** with columns: Season, WeekStart, YearWeek, WeekNum
- Built **TblRates** (room pricing reference) and **TblBookings** tables
- Designed **Dashboard Page 1** with:
  - 📊 Total Revenue Card (₹1 Billion+)
  - 📊 ADR Card (₹15K average)
  - 📊 RevPAR Card
  - 📊 Occupancy % Card (41% average)
  - 📈 Revenue by Month visual
  - 📈 Occupancy % by Month visual
  - 🔽 Year Slicer (2023–2026)

### Module 4 — Forecasting & Cancellation Trend Analysis
- **Objective:** Analyze hotel booking patterns to identify operational and financial inefficiencies using forecasting and trend analysis
- **New DAX Measures Created:**
  - `CancellationFlag` — classifies each booking as Cancelled (Yes) or Not (No)
  - `CancellationRate` — ratio of cancelled bookings to total bookings
  - `RefundAmount` — revenue lost due to cancelled bookings
  - `RefundFlag` — identifies bookings that resulted in a refund
  - `NoShowFlag` — identifies guests who did not arrive despite confirmed booking
  - `NoShowCount` — total count of no-show bookings
  - `NoShowRate` — percentage of no-shows out of total bookings
  - `RoomRate` — room price pulled from Rooms table using RELATED()
  - `DADR` — Derived Average Daily Rate based on room pricing
- **4 Visualizations on new dashboard page "Forecasting & Cancellation Trends":**
  - 📈 **Booking Demand Forecast** — historical booking trends with 7-month forecast (95% confidence interval) using Power BI built-in forecasting
  - 📈 **Cancellation Rate Trend** — monthly cancellation rate variation showing seasonal patterns
  - 📊 **Booking Distribution by Lead Time** — how far in advance customers book rooms
  - 📊 **Monthly Refund Amount vs No-Show Rate** — combo chart comparing financial loss vs operational inefficiency
- **Key Insights:**
  - Booking demand is stable but lacks strong growth — promotional campaigns needed
  - Cancellation rates fluctuate seasonally — stricter policies recommended
  - Mid-range lead time bookings dominate — opportunity for early booking discounts
  - Refunds and no-shows significantly impact revenue — partial refund policies suggested

### Module 3 — Guest Segmentation & RFM Analysis
- **Objective:** Analyze guest behavior to identify valuable customers and support business decision-making
- **Guest Type Segmentation:** Created `GuestType` calculated column using DAX (`SWITCH`, `CALCULATE`) classifying guests as Business, Family, Corporate, or Solo
- **Customer Cluster Segmentation:** Categorized customers into:
  - 🥇 **High Value** — high booking frequency + high revenue
  - 🔄 **Regular** — average booking behavior
  - 🆕 **First-Timer** — new customers
- **Data Transformation:** Created `Tbl_Guests` table converting booking-level data to customer-level data with FirstStay, LastStay, and aggregated metrics
- **RFM Analysis:**
  - **Recency** — days since last stay
  - **Frequency** — total bookings per customer
  - **Monetary (SpendScore)** — total revenue per customer
- **RFM Segmentation:** Customers classified into:
  - 👑 **VIP** — high-value, frequent, recent customers
  - 💙 **Loyal** — consistently frequent customers
  - ⚠️ **At Risk** — customers showing signs of churn
  - 📋 **Regular** — average behavior customers
- **Key Insights:**
  - VIP customers contribute significantly to total revenue
  - At Risk customers can be targeted with promotional offers to reduce churn
  - VIP customers can be retained through loyalty programs

### Module 5 — Dynamic Pricing & Ancillary Revenue Analysis
- **Objective:** Design and develop a dynamic pricing system using Power BI, calculating recommended room prices based on seasonal demand, pricing adjustments, and occupancy sensitivity. Integrate ancillary revenue analysis for data-driven decision-making
- **New Tables Used:** Ancillary_Transactions (spa, dining, services revenue — 25,000 rows)
- **New DAX Measures Created:**
  - `Recommended Price` — dynamically calculates optimized room price using BaseADR × (1 + SeasonAdj + Uplift) × Elasticity
  - Season adjustments: Winter Peak (+15%), Spring (+5%), Summer (-5%), Monsoon (-10%)
- **What-If Parameters Created:**
  - `Price Uplift (%)` — user-controlled slider to simulate pricing strategies (range: -0.20 to 0.20)
  - `Occupancy Sensitivity` — controls pricing aggressiveness based on demand (range: 0.8 to 1.2)
- **5 Visualizations on new dashboard page "Revenue Strategy & Dynamic Pricing":**
  - 💰 **Recommended Price Card** — dynamic KPI card showing real-time recommended price (₹4.89K)
  - 📊 **Pricing Matrix** — room type vs season matrix with conditional formatting showing prices across all 30 room types and 5 seasons
  - 🥧 **Ancillary Revenue Pie Chart** — service contribution breakdown (Spa 73%, Services 27%)
  - 📊 **Ancillary Revenue Trend Chart** — stacked column chart of monthly revenue by service type (Dining, Services, Spa)
  - 🔽 **Interactive Slicers** — Season, Price Uplift (%), Occupancy Sensitivity for dynamic filtering
- **Key Insights:**
  - Winter Peak drives highest recommended prices due to strong demand
  - Monsoon requires lower pricing to maintain occupancy levels
  - Spa services contribute the highest ancillary revenue share — strong upselling opportunity
  - Dynamic pricing parameters enable flexible revenue optimization strategies

---

| Tool | Usage |
|------|-------|
| **Microsoft Excel** | Data generation, data cleaning, calculated columns |
| **Power BI Desktop** | Data modeling, DAX calculations, dashboard design |
| **DAX** | KPI measures (ADR, RevPAR, Occupancy%), RFM scores, segmentation logic |
| **Power Query** | Data transformation, table creation, type corrections |

---

## 📊 Key KPIs Tracked

- **Total Revenue** — Overall money generated across all branches
- **ADR (Average Daily Rate)** — Average price earned per room per night
- **RevPAR (Revenue Per Available Room)** — Revenue efficiency metric combining pricing and occupancy
- **Occupancy %** — Percentage of available rooms that are filled
- **RFM Score** — Customer value score based on Recency, Frequency, Monetary behavior
- **CancellationRate** — Ratio of cancelled to total bookings
- **NoShowRate** — Percentage of no-show bookings
- **RefundAmount** — Total revenue lost due to cancellations
- **Recommended Price** — Dynamically optimized room price based on season and demand
- **Ancillary Revenue** — Additional service revenue from spa, dining, and services

---

## 💡 Business Insights

- Seasonal revenue trends reveal peak and off-peak periods for pricing strategy
- RFM segmentation enables targeted marketing campaigns for different customer groups
- At Risk customers identified for re-engagement campaigns
- Branch-level performance comparison enables resource allocation decisions
- Room type revenue analysis supports dynamic pricing strategies
- Dynamic pricing simulation shows Winter Peak drives highest revenue potential
- Spa services identified as top ancillary revenue contributor for upselling focus
- Cancellation and no-show patterns quantified to minimize revenue loss

---

## 📅 Internship Details

| Detail | Info |
|--------|------|
| Program | Infosys Springboard Virtual Internship 6.0 |
| Domain | Data Analytics & Business Intelligence |
| Tool | Power BI |
| Duration | Mar 2026 – Apr 2026 |
| Modules Completed | ✅ 5 of 5 — Project Complete |

---

> *This project demonstrates end-to-end data analytics skills including data generation, data modeling, DAX-based KPI development, customer segmentation, forecasting, dynamic pricing, and interactive dashboard design using Power BI — built as part of the Infosys Springboard Virtual Internship 6.0.*
