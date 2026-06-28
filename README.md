# Business Data Cleaning, Validation & Excel Reporting

## Problem Summary

The objective of this project was to clean, validate, and prepare a retail orders dataset for business reporting. The dataset contained missing values, duplicate records, inconsistent discount values, and invalid records that required validation before analysis. Data cleaning was performed using Microsoft Excel by applying business rules, creating calculated columns, validating data quality, and generating summary reports.

---

## Dataset Description

The dataset contains retail order transactions with customer, product, sales, shipping, and payment information.

Key fields include:

- Order ID
- Order Date
- Ship Date
- Customer ID
- Customer Segment
- Region
- Category
- Sub-Category
- Product Name
- Quantity
- Unit Price
- Discount
- Cost
- Payment Status
- Ship Mode

---

## Tools Used

- Microsoft Excel
- Excel Formulas
- Pivot Tables
- Conditional Formatting
- Filters and Sorting

---

## Data Cleaning Steps

The following cleaning activities were completed:

- Standardized text values.
- Filled missing **Region** values with **Unknown**.
- Filled missing **Ship Mode** values with **Unknown**.
- Reviewed duplicate records and identified exact and conflicting duplicates.
- Created a **Cleaned_discount** column.
- Replaced missing discount values with **0** only when **Quantity × Unit Price = Cost**.
- Marked remaining missing discount values as **Unknown**.
- Flagged negative discount values.
- Flagged discount values greater than **1**.
- Validated shipping dates.
- Created calculated business columns.
- Generated data quality and pivot summary reports.

---

## Business Rules Applied

- Missing Region values were filled with **Unknown**.
- Missing Ship Mode values were filled with **Unknown**.
- Missing Discount values were treated as **0** only when **Quantity × Unit Price = Cost**; otherwise they were marked as **Unknown**.
- Negative discount values were flagged as invalid.
- Discount values greater than **1** were flagged as invalid.
- Cancelled orders were excluded from completed sales summaries.
- Failed payment orders were excluded from completed sales summaries.
- Refunded orders were retained for separate reporting.
- Ship Date earlier than Order Date was flagged as an invalid shipping record.

---

## Calculated Columns Created

The following calculated columns were added:

- Cleaned_discount
- Calculated_sales
- Calculated_profit
- Profit_margin
- Shipping_delay_days
- Order_month
- Order_year
- Data_quality_flag

---

## Outputs Generated

The following project outputs were created:

- cleaned_orders.xlsx
- data_quality_report.xlsx
- pivot_summary.xlsx
- cleaning_log.md

---

## Key Outcome

The dataset was successfully cleaned and validated by handling missing values, identifying duplicate records, validating discount values, applying business rules, creating calculated columns, and generating business-ready reports. The final dataset is suitable for reporting and further business analysis.