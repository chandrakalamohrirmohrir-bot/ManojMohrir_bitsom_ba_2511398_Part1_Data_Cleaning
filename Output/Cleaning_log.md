# Cleaning Log

## Business Rules Applied

| Rule Area | Action Taken |
|-----------|--------------|
| Missing Region | Missing region values were filled with **Unknown**. |
| Missing Ship Mode | Missing ship mode values were filled with **Unknown**. |
| Missing Discount | Blank discount values were replaced with **0** only when **Quantity × Unit Price = Cost**. Remaining blank values were marked as **Unknown**. |
| Negative Discount | Negative discount values were flagged as **Invalid-Negative Discount** in the Discount_flag column. |
| Discount Above Allowed Range | Discounts greater than **1** were flagged as **Invalid-Above Allowed Range** in the Discount_flag column. |
| Cancelled Orders | Cancelled orders were retained in the dataset but should not contribute to the completed sales summary. |
| Failed Payments | Failed payment records were retained in the dataset but should not contribute to the completed sales summary. |
| Refunded Orders | Refunded payment records were retained and should be summarized separately during analysis. |
| Ship Date Before Order Date | Shipping records with ship date before order date were flagged as **Invalid** in the Shipping date flag column. |

## Summary

- Missing **Region** values were replaced with **Unknown**.
- Missing **Ship Mode** values were replaced with **Unknown**.
- Missing **Discount** values were treated as **0** only when business rules confirmed no discount was applied; otherwise they were marked as **Unknown**.
- Duplicate records were identified as **Exact Duplicate** or **Conflicting Duplicate** without removing conflicting records.
- Invalid discount values (negative or greater than **1**) were flagged.
- Date validations were performed, including ship date occurring before order date.
- Calculated Sales, Calculated Profit and Profit Margin were derived using the cleaned discount values.
- Records with unresolved issues were marked as **Needs Review** in the **Data_quality_Flag** column.

## Task 9

## 1. List of Issues Found

- Missing values in **Region**.
- Missing values in **Ship Mode**.
- Missing values in **Discount**.
- Exact duplicate records.
- Duplicate Order IDs with conflicting information.
- Negative discount values.
- Discount values greater than **1**.
- Records where Ship Date was earlier than Order Date.
- Missing discount values that could not be reliably determined.

---

## 2. Cleaning Actions Performed

- Standardized text values where required.
- Filled missing **Region** values with **Unknown**.
- Filled missing **Ship Mode** values with **Unknown**.
- Created **Cleaned_discount** column.
- Replaced missing discount values with **0** only when **Quantity × Unit Price = Cost**.
- Marked remaining missing discount values as **Unknown**.
- Created calculated columns:
  - Calculated Sales
  - Calculated Profit
  - Profit Margin
  - Shipping Delay Days
  - Order Month
  - Order Year
  - Data Quality Flag
- Identified duplicate records and flagged conflicting duplicates.
- Flagged invalid discount values.
- Validated shipping dates.

---

## 3. Business Rules Applied

- Missing Region → Filled with **Unknown**.
- Missing Ship Mode → Filled with **Unknown**.
- Missing Discount → Filled with **0** only when **Quantity × Unit Price = Cost**; otherwise marked as **Unknown**.
- Negative Discount → Flagged as **Negative Discount**.
- Discount > 1 → Flagged as **Invalid - Above Allowed Range**.
- Cancelled orders were retained but excluded from completed sales summaries.
- Failed payment orders were retained but excluded from completed sales summaries.
- Refunded orders were retained and summarized separately.
- Ship Date before Order Date was flagged as an invalid shipping record.

---

## 4. Assumptions Made

- A blank discount was treated as **0** only when **Quantity × Unit Price = Cost**.
- Remaining blank discount values were considered **Unknown** because the correct discount could not be inferred.
- Conflicting duplicate records were retained for manual review instead of being deleted.

---

## 5. Records Removed

- No records were removed from the dataset.

---

## 6. Records Flagged

- Conflicting duplicate records were flagged for review.
- Negative discount values were flagged.
- Discount values greater than **1** were flagged.
- Records with **Unknown** discount values were flagged through the **Data Quality Flag**.
- Records with Ship Date earlier than Order Date were flagged.

---

## 7. Limitations

- Unknown discount values could not be calculated because sufficient information was unavailable.
- Conflicting duplicate records require manual verification before removal.
- Calculated Sales, Calculated Profit and Profit Margin remain **Unknown** for records with **Unknown** discount values.