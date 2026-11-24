# NexaMart 2026 — Executive Operations & Financial BI Dashboard

An end-to-end Excel Business Intelligence capstone project tracking order fulfillment, net revenue, gross profit margin, acquisition channels, brand performance, and regional manager SLA delivery speed across **Jan–Sep 2026**.

## Key Highlights & Metrics (Jan–Sep 2026)
- **Total Orders:** 300 (223 On-Time, 77 Delayed)
- **Units Sold:** 750 (Avg. 2.5 items per order)
- **Net Revenue:** ₹51,86,031 (₹5,186.0K | ₹17,287 avg. per order)
- **Gross Profit:** ₹2,287.5K (44.1% profit margin)
- **SLA Breach Rate:** 25.7% (77 of 300 orders)

## Data Architecture & Modeling
- **Star-Schema Data Model:** Integrated order, product, and warehouse/regional dimension tables (`07_PQ_Regional_Orders`, `08_Dim_Products`, `09_Dim_Warehouses`, etc.) in Excel's Data Model / Power Pivot.
- **Measures & Helper Tables:** Built pivot-driven helper tables and `GETPIVOTDATA` formulas on `12_Data_Model_Pivot` to feed dynamic KPIs, charts, and the Regional Manager Scorecard.
- **3-Tier SLA Status Logic:** Evaluates actual average delivery days against each manager's `Target_SLA_Days` using a `0.3`-day warning buffer:
  - **On Track (`1` / Green):** Actual days `< Target SLA - 0.3`
  - **Watchlist (`0` / Yellow):** Actual days between `Target SLA - 0.3` and `Target SLA`
  - **SLA Alert (`-1` / Red):** Actual days `> Target SLA`

## Dashboard Design & Export
- **Custom Slicer Theme:** Designed a dark-navy and teal slicer theme (`Region`, `Order Status`, `Customer Segment`, `Regional Manager`) with clean single-column layout and `Hide items with no data` enabled.
- **Single-Page Print/PDF Ready:** Configured print area, margins, and layout scaling on `13_Dashboard` for clean single-page executive viewing.

## Repository Structure
- `NexaMart_2026_Excel_Capstone_Workbook.xlsx` — Complete Excel workbook with data model, pivots, helper tables, and dashboard.
- `NexaMart_2026_Excel_Capstone_Workbook.pdf` — Single-page exported dashboard snapshot.
- `assets/dashboard_preview.png` — Dashboard preview image.
