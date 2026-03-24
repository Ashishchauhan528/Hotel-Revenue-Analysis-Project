# 🏨 Hotel Revenue Analytics Dashboard
### Infosys Springboard Virtual Internship 6.0

## 📌 Project Overview

This project was developed as part of the **Infosys Springboard Virtual Internship 6.0** program. The objective is to build a comprehensive **Hotel Revenue Analytics Dashboard** using Power BI, covering data generation, data modeling, KPI analysis, customer segmentation, and RFM (Recency, Frequency, Monetary) analysis for a hotel chain operating across multiple branches in India.

The dataset was self-generated to simulate real-world hotel operations across 15 branches and 4,000+ customers, covering booking data from 2023 to 2026.

Submitted By
**Ashish Chauhan**
Infosys Springboard Virtual Internship 6.0

## 🗂️ Project Structure

```
Hotel-Revenue-Analytics/
│
├── Module_1/       → Data Generation, Data Modeling & Star Schema
├── Module_2/       → KPI Calculations, Master Data & Dashboard Page 1
├── Module_3/       → Guest Segmentation & RFM Analysis
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

---

## 🛠️ Tools & Technologies

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

---

## 💡 Business Insights

- Seasonal revenue trends reveal peak and off-peak periods for pricing strategy
- RFM segmentation enables targeted marketing campaigns for different customer groups
- At Risk customers identified for re-engagement campaigns
- Branch-level performance comparison enables resource allocation decisions
- Room type revenue analysis supports dynamic pricing strategies

---

## 📅 Internship Details

| Detail | Info |
|--------|------|
| Program | Infosys Springboard Virtual Internship 6.0 |
| Domain | Data Analytics & Business Intelligence |
| Tool | Power BI |
| Duration | Mar 2026 – Apr 2026 |
| Modules Completed | 3 of 6 (Dashboard & Documentation in progress) |

---

## 🚀 Upcoming (Module 4–6)
- Advanced dashboard pages (branch-level, room-type analysis)
- Final interactive dashboard with complete drill-through
- Project documentation and final presentation

---

> *This project demonstrates end-to-end data analytics skills including data generation, data modeling, DAX-based KPI development, customer segmentation, and interactive dashboard design using Power BI.*
