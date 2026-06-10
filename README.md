<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,30&height=200&section=header&text=FINVIEW%20%E2%80%94%20Finance%20Analysis%20Dashboard&fontSize=34&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Power%20BI%20%7C%20Real-Time%20Insights%20into%20Transactions%2C%20Customers%20%26%20Risk&descAlignY=58&descSize=15"/>

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)](#)
[![Pages](https://img.shields.io/badge/Pages-2%20Report%20Pages-8B5CF6?style=for-the-badge)](#)
[![Drill Down](https://img.shields.io/badge/Drill--Down-Enabled-EC4899?style=for-the-badge)](#)
[![Domain](https://img.shields.io/badge/Domain-Finance%20%26%20Banking-06B6D4?style=for-the-badge)](#)
[![Status](https://img.shields.io/badge/Status-Complete-22C55E?style=for-the-badge)](#)

</div>

---

## 📌 Project Overview

**FINVIEW** is a two-page, fully interactive Power BI dashboard built to give finance teams, analysts, and business stakeholders real-time visibility into transaction performance, customer behaviour, and risk metrics.

The dashboard connects a **Customers dimension table** and a **Finance Transactions fact table** to deliver executive-grade KPIs, trend analysis, and granular drill-down into individual transaction records — all filterable by Year, Dynamic Metric, Occupation, and Category.

---

## 🖼️ Dashboard Preview

### Page 1 — Overview Analysis
<img width="1369" height="718" alt="Screenshot 2026-06-10 122158" src="https://github.com/user-attachments/assets/20d0c827-3b05-4a42-93d2-ef9761518d67" />


### Page 2 — Transactions (Drill-Down)
<img width="1371" height="720" alt="Screenshot 2026-06-10 122220" src="https://github.com/user-attachments/assets/40eb1ced-4eed-4993-b5a9-8a87bd60cf18" />


> 📁 Drop your screenshots into an `assets/` folder and rename them to match the paths above.

---

## 🗂️ Report Pages

This dashboard has **2 report pages**, each serving a distinct analytical purpose:

| Page | Name | Purpose |
|------|------|---------|
| 1️⃣ | **Overview Analysis** | High-level KPI summary, monthly trends, state-wise and segment-wise performance |
| 2️⃣ | **Transactions** | Granular row-level transaction detail table with drill-down capability |

---

## 🎯 Key KPIs (Header Cards — Both Pages)

These 5 KPI cards appear across both pages and update dynamically based on the selected slicers:

| KPI Card | 2025 Value | YoY Change | What it measures |
|----------|-----------|------------|-----------------|
| 💰 **Total Amount** | ₹ 1.86M | ▲ 12.88% vs PY | Total transaction amount for the selected period |
| 🔢 **Total Transactions** | 166 | ▼ 16.16% vs PY | Count of all transaction records |
| 📊 **Avg Transaction Value** | ₹ 11.19K | ▲ 34.64% vs PY | Average rupee value per transaction |
| 💸 **Total Fees** | ₹ 3.07K | ▲ 12.92% vs PY | Total fees collected across all transactions |
| 🧾 **Total Tax** | ₹ 552.77 | ▲ 12.92% vs PY | Total tax collected across all transactions |

> **YoY Change** — Each card shows percentage change vs the Previous Year, calculated using DAX time intelligence measures.

---

## 📊 Page 1 — Overview Analysis (All Visuals)

| Visual | Chart Type | Fields Used | Key Insight |
|--------|-----------|-------------|-------------|
| **Total Amount by Month** | Area + Line Chart | transaction_date (Month), Amount | Peaks in Apr, Aug — dip in Jan & Oct |
| **Total Amount by Transaction Status** | Donut Chart | transaction_status, Amount | 73.5% Success (₹1.4M) · 18.8% Pending · 7.7% Failed |
| **Total Amount by Customer Segment** | Horizontal Bar | customer_segment, Amount | Retail leads · Wealth lowest at ₹0.03M |
| **Total Amount by State** | Horizontal Bar | state, Amount | Gujarat #1 · followed by Haryana & Uttar Pradesh |
| **Transaction Type Analysis** | Matrix Table | transaction_type, Amount, Fees, Tax, Transaction count | Loan EMI is highest — ₹0.7M amount, ₹1.2K fees |
| **Total Amount by Gender** | Donut Chart | gender, Amount | Female 52.1% (₹1.0M) · Male 47.9% (₹0.9M) |

---

## 🔍 Page 2 — Transactions (Drill-Down Table)

This page contains a **detailed transaction-level table** with drill-down functionality, showing every individual transaction record.

### Columns displayed in the table:

| Column | Source | Description |
|--------|--------|-------------|
| `Transaction Id` | finance_transactions | Unique transaction identifier (e.g. T00010610) |
| `Transaction Date` | finance_transactions | Date of the transaction (e.g. 23 August 2025) |
| `Name` | customers (joined) | Customer full name from dimension table |
| `Transaction Type` | finance_transactions | Type: Loan EMI, Transfer, Card Payment, Deposit, etc. |
| `Transaction Status` | finance_transactions | Success / Pending / Failed |
| `Gender` | customers (joined) | Male / Female |
| `Customer Segment` | customers (joined) | Retail / SME / Corporate / Premium / Wealth |
| `State` | customers (joined) | Indian state of the customer |
| `Total Amount` | finance_transactions | Transaction amount in ₹ |
| `Total Fees` | finance_transactions | Fee charged on the transaction |
| `Total Tax` | finance_transactions | Tax applied on the transaction |

### 🔎 Drill-Down Feature

The Transactions page includes **drill-down** enabled on the transaction date hierarchy:

```
Year  ──►  Quarter  ──►  Month  ──►  Day
```

- Click the **drill-down arrow** on the table header to go deeper into date granularity
- This lets you move from a yearly summary all the way down to individual day-level transactions
- Combined with the **Year slicer**, you can isolate any specific time window instantly

> **How to use it in Power BI:**
> Right-click any row in the date column → Select **Drill Down**
> Or use the drill arrows in the top-right corner of the visual

---

## 🎛️ Interactive Slicers (Filters)

All visuals on both pages respond to these four slicers on the left panel:

| Slicer | Field | What it controls |
|--------|-------|-----------------|
| 📅 **Year** | transaction_date (Year) | Filters entire report to selected year — currently set to 2025 |
| 📐 **Dynamic Metric** | Custom DAX field parameter | Switches the metric shown across visuals (Total Amount, Fees, Tax, etc.) |
| 👔 **Occupation** | customers[occupation] | Filters by customer job type — currently set to Salaried |
| 🏷️ **Category** | transaction type group | Filters by transaction category — currently set to Rent |

> **Dynamic Metric slicer** is powered by a **Field Parameter** — a Power BI feature that lets the user switch between measures without changing the report layout. This is an advanced Power BI technique.

---

## 🧮 DAX Measures Used

All DAX measures are stored in a dedicated **measures table** (best practice). Below is every measure used in this dashboard:

---

### 📦 Core Amount Measures

```dax
-- Total transaction amount
Total Amount =
    SUM(finance_transactions[amount])

-- Total fees collected
Total Fees =
    SUM(finance_transactions[fee_amount])

-- Total tax collected
Total Tax =
    SUM(finance_transactions[tax_amount])

-- Total number of transactions
Total Transactions =
    COUNTROWS(finance_transactions)

-- Average value per transaction
Avg Transaction Value =
    DIVIDE([Total Amount], [Total Transactions], 0)
```

---

### 📅 Time Intelligence — Year-over-Year (YoY)

```dax
-- Previous Year Total Amount
PY Total Amount =
    CALCULATE(
        [Total Amount],
        SAMEPERIODLASTYEAR('Date'[Date])
    )

-- YoY Change Amount
YoY Change Amount =
    [Total Amount] - [PY Total Amount]

-- YoY Change % (shown on all KPI cards)
YoY Change % =
    DIVIDE(
        [YoY Change Amount],
        [PY Total Amount],
        0
    ) * 100

-- Previous Year Total Transactions
PY Total Transactions =
    CALCULATE(
        [Total Transactions],
        SAMEPERIODLASTYEAR('Date'[Date])
    )

-- YoY % for Transactions
YoY Transactions % =
    DIVIDE(
        [Total Transactions] - [PY Total Transactions],
        [PY Total Transactions],
        0
    ) * 100

-- Previous Year Fees
PY Total Fees =
    CALCULATE(
        [Total Fees],
        SAMEPERIODLASTYEAR('Date'[Date])
    )

-- YoY % for Fees
YoY Fees % =
    DIVIDE(
        [Total Fees] - [PY Total Fees],
        [PY Total Fees],
        0
    ) * 100

-- Previous Year Tax
PY Total Tax =
    CALCULATE(
        [Total Tax],
        SAMEPERIODLASTYEAR('Date'[Date])
    )

-- YoY % for Tax
YoY Tax % =
    DIVIDE(
        [Total Tax] - [PY Total Tax],
        [PY Total Tax],
        0
    ) * 100
```

---

### 🔄 Dynamic Metric (Field Parameter)

```dax
-- Field Parameter for Dynamic Metric slicer
-- This allows users to switch metrics across all visuals
Dynamic Metric =
{
    ("Total Amount",    NAMEOF('Measures'[Total Amount]),    0),
    ("Total Fees",      NAMEOF('Measures'[Total Fees]),      1),
    ("Total Tax",       NAMEOF('Measures'[Total Tax]),       2),
    ("Avg Txn Value",   NAMEOF('Measures'[Avg Transaction Value]), 3)
}
```

---

### 📊 Status & Segment Analysis

```dax
-- Amount for Successful transactions only
Success Amount =
    CALCULATE(
        [Total Amount],
        finance_transactions[transaction_status] = "Success"
    )

-- Amount for Failed transactions only
Failed Amount =
    CALCULATE(
        [Total Amount],
        finance_transactions[transaction_status] = "Failed"
    )

-- Amount for Pending transactions only
Pending Amount =
    CALCULATE(
        [Total Amount],
        finance_transactions[transaction_status] = "Pending"
    )

-- % of total for each status (used in donut chart labels)
Transaction Status % =
    DIVIDE(
        [Total Amount],
        CALCULATE([Total Amount], ALL(finance_transactions[transaction_status])),
        0
    ) * 100
```

---

### 🌍 Geographic & Segment Measures

```dax
-- Rank states by Total Amount (used to sort bar chart)
State Rank =
    RANKX(
        ALL(customers[state]),
        [Total Amount],
        ,
        DESC,
        DENSE
    )

-- Top N States filter measure
Top 10 States =
    IF([State Rank] <= 10, 1, 0)
```

---

### 🚨 Risk & Fraud Measures

```dax
-- Average risk score across transactions
Avg Risk Score =
    AVERAGE(finance_transactions[risk_score])

-- Count of fraud transactions
Fraud Count =
    CALCULATE(
        COUNTROWS(finance_transactions),
        finance_transactions[is_fraud] = "Yes"
    )

-- Fraud rate as a percentage
Fraud Rate % =
    DIVIDE([Fraud Count], [Total Transactions], 0) * 100
```

---

## 🗃️ Data Model

### Tables

| Table | Type | Rows | Role |
|-------|------|------|------|
| `finance_transactions` | **Fact Table** | 50,069 | All transaction events — amounts, fees, tax, status, fraud |
| `customers` | **Dimension Table** | 5,000 | Customer profile — name, gender, city, state, segment, occupation |
| `Date` | **Date Table** | 365+ | Dedicated calendar table for time intelligence DAX functions |
| `Measures` | **Measures Table** | — | Stores all DAX measures (no data rows) |

### Relationships

```
customers                          finance_transactions
────────────────                   ──────────────────────
customer_id (PK) ◄──────────────── customer_id (FK)
first_name                         transaction_id
gender                             transaction_date ──────► Date[Date]
city                               amount
state                              fee_amount
occupation                         tax_amount
customer_segment                   transaction_type
annual_income                      transaction_status
                                   is_fraud
                                   risk_score
```

**Relationship type:** One-to-Many (`customers` → `finance_transactions`)
**Date table:** Mark as Date Table → enables SAMEPERIODLASTYEAR and all time intelligence functions

---

## 📁 Repository Structure

```
finview-finance-analysis-powerbi/
│
├── 📊 FinView_Finance_Analysis.pbix     ← Main Power BI file
├── 📄 README.md                          ← You are here
│
├── 📁 assets/
│   ├── overview_analysis.png             ← Page 1 screenshot
│   └── transactions.png                  ← Page 2 screenshot
│
├── 📁 data/
│   ├── customers.csv                     ← Dimension table (5,000 rows)
│   └── finance_transactions.csv          ← Fact table (50,069 rows)
│
└── 📁 dax/
    └── all_measures.dax                  ← All DAX measures exported as text
```

---

## 🚀 How to Use

1. **Clone this repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/finview-finance-analysis-powerbi.git
   ```

2. **Open in Power BI Desktop**
   - Open `FinView_Finance_Analysis.pbix`
   - Free download: [Power BI Desktop](https://powerbi.microsoft.com/desktop/)

3. **Load the data**
   - Go to **Home → Transform Data → Data Source Settings**
   - Point to the `data/` folder CSVs

4. **Explore the dashboard**
   - Use **Year**, **Dynamic Metric**, **Occupation**, and **Category** slicers to filter
   - Switch between **Overview Analysis** and **Transactions** pages using the left navigation
   - On the Transactions page — use the **drill-down arrows** on dates to go from Year → Month → Day

---

## 💡 Key Business Insights

| # | Insight |
|---|---------|
| 1 | **73.5%** of total transaction value is from successful transactions — ₹1.4M out of ₹1.86M |
| 2 | **Loan EMI** is the highest revenue-generating transaction type at ₹0.7M |
| 3 | **Gujarat** leads all states in transaction volume — significantly ahead of Haryana (₹0.21M) |
| 4 | **Retail segment** dominates — far ahead of SME (₹0.30M) and Corporate (₹0.23M) |
| 5 | **Female customers** generate slightly more volume — 52.1% (₹1.0M) vs Male 47.9% (₹0.9M) |
| 6 | **April and August** are peak transaction months — visible in the area chart |
| 7 | **Total transactions dropped 16.16% YoY** — but Total Amount grew 12.88%, showing higher-value fewer deals |

---

## 🛠️ Tech Stack

| Tool | Usage |
|------|-------|
| **Power BI Desktop** | Dashboard design, data modeling, report publishing |
| **DAX** | All KPI measures, YoY time intelligence, dynamic metrics, ranking |
| **Power Query (M)** | Data cleaning, column type formatting, table merging |
| **Field Parameters** | Dynamic Metric slicer — switch measures without changing visuals |
| **Drill-Down** | Date hierarchy navigation on Transactions page |

---

## 📬 Connect with Me

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR_PROFILE)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/YOUR_USERNAME)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:YOUR_EMAIL)

</div>

---

<div align="center">

**⭐ If this project helped you, please give it a star — it helps others discover it!**

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,30&height=100&section=footer"/>

</div>
