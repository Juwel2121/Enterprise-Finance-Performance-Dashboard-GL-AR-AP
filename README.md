# Enterprise Finance Performance Dashboard (GL • AR • AP)

## Overview
This Power BI project delivers a **3-page enterprise finance dashboard** that covers:
- **Finance Overview + General Ledger (GL)**
- **Accounts Receivable (AR) + Sales**
- **Accounts Payable (AP) + Expense Details**

It’s designed for fast decision-making: users can monitor **revenue, costs, profitability**, and drill down into **invoice-level** and **transaction-level** details using slicers and tables.

---

## Report Preview (Screenshots)

### Finance Overview & GL
![Finance Overview & GL](https://raw.githubusercontent.com/Juwel2121/Enterprise-Finance-Performance-Dashboard-GL-AR-AP/main/Images/Finance%20Overview%20%26%20GL.jpg)

### Accounts Receivable & Sales
![Accounts Receivable & Sales](https://raw.githubusercontent.com/Juwel2121/Enterprise-Finance-Performance-Dashboard-GL-AR-AP/main/Images/Accounts%20Receiveable%20%26%20Sales.jpg)

### Accounts Payable & Expense Details
![Accounts Payable & Expense Details](https://raw.githubusercontent.com/Juwel2121/Enterprise-Finance-Performance-Dashboard-GL-AR-AP/main/Images/Accounts%20Payble%20%26%20Expense%20Details.jpg)

---

## What this report helps you answer
### Finance (GL)
- How are **Revenue vs Expenses** trending by month/year?
- What are **COGS**, **Gross Margin %**, and **Net Profit %** over time?
- Which **accounts** drive revenue and expenses the most?
- What are the key **GL transactions** behind a spike/drop?

### Accounts Receivable (AR) & Sales
- How much AR is **open** and what % is still unpaid?
- Which customers have the **highest outstanding balances**?
- What is the AR distribution by **aging bucket** (0–30, 31–60, 61–90, 90+, Not Overdue)?
- Which invoices are **Open / Partial / Received**?

### Accounts Payable (AP) & Expenses
- How much AP is open and how much is already paid?
- Which vendors have the **largest AP exposure**?
- Which departments consume the **highest expenses**?
- Which expense categories (Supplies/Meals/Travel/Training/etc.) are driving spend?

---

## Folder structure (Typical)
- **PBIX/**
  - Power BI report file
- **Database/**
  - Excel datasets (AR, AP, GL, Expenses, Budget/Forecast, dimensions)
- **Documents/**
  - PDF export / supporting docs
- **Images/**
  - Report page screenshots

---

## Data model (high level)
This report follows a **finance star-schema style** model with core operational datasets:

### Core fact-style tables
- **General Ledger (GL)**: transaction-level accounting entries (debit/credit) by date, account, department
- **Accounts Receivable (AR)**: customer invoices with status and aging
- **Accounts Payable (AP)**: vendor invoices with status and aging
- **Expense Claims**: employee expense submissions and approvals
- **Budget / Forecast**: planned values for comparison (if enabled)

### Common dimensions
- **Date**
- **Customer**
- **Vendor**
- **Employee**
- **Department**
- **Currency** (if multi-currency is enabled)

---

## Report pages (what you’ll see)

### 1) Finance Overview & GL
Focus: **top KPIs + monthly trend + GL drilldown**
- KPI cards: Revenue, COGS, Expenses, Gross Margin %, Net Profit %, Revenue MTD, Revenue YTD
- Revenue & Expenses trend by month/year
- Revenue/Expense breakdown by account
- GL Transaction detail table (drill down by date/account/department)
- Revenue comparison: YTD vs MTD across years

---

### 2) Accounts Receivable & Sales
Focus: **AR exposure, aging, and customer concentration**
- KPI cards: Total Customers, Total AR Invoices, Open Invoices, AR Amount, AR Open Amount, AR Open %
- AR Amount trend by month/year
- AR Amount by Aging Bucket (0–30 / 31–60 / 61–90 / 90+ / Not OverDue)
- AR Aging matrix by customer
- Top customers by outstanding AR
- Sales Register (invoice-level detail)

---

### 3) Accounts Payable & Expense Details
Focus: **vendor dues + expense drivers**
- KPI cards: Total Vendors, Total AP Invoices, AP Amount, AP Open Amount, Expense Amount, AP Open %
- AP Amount by Aging Bucket
- Top vendors by AP amount
- Expense Amount by Department
- Expense Amount by Category
- AP Aging matrix by vendor
- Expense claims detail + purchase register tables

---

## Common slicers/filters available
- Date range (timeline)
- Department
- Status (Open / Partial / Received / Paid)
- Customer (AR page)
- Vendor + Employee (AP/Expense page)
- Month-Year quick filter

---

## KPI definitions (plain language)
- **Revenue**: total income recorded in revenue accounts
- **COGS**: direct costs linked to revenue
- **Expenses**: operational spending (travel, supplies, etc.)
- **Gross Margin %**: (Revenue − COGS) / Revenue
- **Net Profit %**: (Revenue − COGS − Expenses) / Revenue
- **MTD / YTD**: month-to-date and year-to-date totals
- **AR Open %**: open AR amount / total AR amount
- **AP Open %**: open AP amount / total AP amount
- **Aging bucket**: unpaid balances grouped by days outstanding

---

## How to open & refresh (Power BI Desktop)
1. Open the `.pbix` file in **Power BI Desktop**
2. If refresh fails after moving folders:
   - Go to **Transform data → Data source settings**
   - Update file paths to the **Database/** Excel files
3. Click **Refresh**

Tip: Keep the same folder structure (PBIX + Database + Documents + Images) to avoid broken paths.

---

## Notes
- This project uses **structured/sample finance datasets** (Excel-based).
- The visuals are built for **interactive drilldown** (charts → tables).
- Aging buckets depend on invoice dates and the report’s aging logic.
