---
title: 'Revenue Chart'
taxonomy:
    category:
        - docs
---

Use **Documents Seller → Revenue Chart** in the Joomla administrator to review sales over time, compare paid revenue with the same period last year, and see how selected documents perform against each other. You can switch between revenue amounts and order counts, filter the data, and download the chart values as a CSV file.

## Review revenue over a selected period

1. Open **Documents Seller → Revenue Chart**.
2. Choose a **Period**, or select **Custom** and enter the first and last months in **From** and **To**.
3. Choose an **Interval** to group the results by week, month, quarter, or year.
4. Leave **Documents** empty to include all documents, or select one or more documents. If the **Category** filter is shown, you can also limit the orders by category.
5. Select **Revenue** and **Total** to see separate lines for paid and refunded orders. Switch to **Orders** to compare order counts instead of amounts.

The chart updates automatically when you change a filter. Hover over a point to see its value. Click a label in the chart legend to hide or show that line.

### Period and interval

| Control | How it works |
| --- | --- |
| **Last 12 months** | Shows the same month last year through the current month, including both endpoint months. For example, in November 2026, the range is November 2025 to November 2026. |
| **This Year** | Shows January through December of the current year. |
| **Last Year** | Shows January through December of the previous year. |
| **Last 3 years** | Shows 36 months ending with the current month. |
| **Custom** | Lets you choose the first and last months. Both months are included, with a maximum range of 120 months. |
| **Interval** | Groups results by **Week**, **Month**, **Quarter**, or **Year**. **Week** is available for ranges of up to three months; longer ranges switch a weekly interval to **Month**. Weeks start on Monday, and quarters follow the calendar year. |
| Previous and next arrows | Move backward or forward by the length of the selected range. For example, a three-month range moves by three months. You can also focus the chart and use the left and right arrow keys. |
| **Today** | Returns to the **Last 12 months** range. |

The range uses whole months. If you select a quarter or year interval for a range that covers only part of that quarter or year, the point includes only orders within your selected months. The current month contains orders recorded so far; keep this in mind when comparing it with a completed month.

## Filter by document or category

Use **Documents** to select one or more products. An order matches when it contains at least one selected document. Remove all selections to return to **All documents**. The selector lists documents with paid or refunded orders in the selected period and category, and keeps documents you have already selected when you change the range.

The **Category** filter appears when there is more than one published category. Selecting a category includes orders containing a document assigned to that category or one of its published child categories.

These filters select whole orders. In **Total** mode, each matching order contributes its full amount or one order, even if its cart also contains other documents. Selecting several documents does not count the same order more than once. In **Per document** mode, the chart divides each matching paid order between its purchased documents as described below. A category filter can therefore include document lines for other products bought in the same cart; select specific documents to limit the lines shown.

## Compare with the previous year

1. Choose the period, interval, and document or category filters you want to review.
2. Select **Total** mode.
3. Enable **Compare with previous year**.

The chart adds a dashed **Paid (previous year)** line using the same filters and the same month range shifted back one year. For example, January–June 2026 is compared with January–June 2025. Choose **Revenue** to compare paid amounts or **Orders** to compare paid order counts.

The previous-year line compares paid orders only. The **Compare with previous year** switch is disabled in **Per document** mode.

## Compare documents

Use **Per document** mode to identify stronger products, compare sales trends, or check whether a product's performance changes over time.

1. Choose a period and interval, such as **This Year** and **Month**.
2. In **Documents**, select the products you want to compare.
3. Select **Per document**.
4. Choose **Revenue** to compare amounts or **Orders** to compare each document's share of paid orders.

The chart draws a separate colored line for each document with matching paid orders. Refunded orders are excluded from these lines. Without a document selection, it shows the top documents by the selected metric for the period. A maximum of 10 document lines is shown, including when you select more than 10 documents. Narrow your selection to compare specific products. A selected document with no matching paid orders has no line.

### How cart orders are shared between documents

For a cart purchase, **Per document** mode divides the final order amount equally between all documents in that order. It does not use their individual item prices. The **Orders** metric uses the same division, so document values can be fractions.

For example, a paid order for `90.00` containing three documents contributes `30.00` in **Revenue**, or one-third of an order in **Orders**, to each document. If you select only one of those documents, its share remains `30.00` or one-third; the full order value is not reassigned to it.

Use the [Sales Report](/orders-management#sales-report) when you need product income based on the prices recorded on order items. That report uses different rules: it includes pending offline orders and calculates income before order-level discounts and tax.

## Understand the totals

The **Paid** and **Refunded** totals below the chart show amounts or order counts for all matching orders in the selected range. They remain order-level totals in **Per document** mode, so they are not totals for individual document lines or only the top 10 documents shown.

Each total can show a percentage change **vs previous period**. This compares the selected range with the immediately preceding range of the same length. For example, April–June is compared with January–March. A percentage is shown only when the corresponding previous-period value is greater than zero.

The summary percentages use this preceding period even when **Compare with previous year** is enabled. The dashed chart line and the summary percentages answer different questions.

### Which orders and amounts are included?

- The chart includes orders currently marked **Paid** or **Refunded**. Pending orders, including pending offline orders, are excluded. After receiving an offline payment, [approve the order](/orders-management#publish-approve-order) to include it as paid.
- Orders are grouped by their **creation date**, using the Joomla site's time zone. Payment and refund dates do not determine the reporting period. An older order that is later marked **Refunded** moves from the paid series to the refunded series in its original creation period.
- **Revenue** uses the final amount recorded on the order, after discounts and including tax. **Refunded** shows the recorded amounts of orders marked refunded as a separate positive series; the chart does not subtract them from **Paid** to calculate a net total.
- **Orders** counts each matching order once in **Total** mode, regardless of how many documents it contains. **Per document** mode shares that count between the purchased documents.

## Export the chart

Set your filters, metric, display mode, and comparison option, then click **CSV** above the chart. The file is named `revenue-YYYY-MM-YYYY-MM.csv`, using the selected start and end months.

The CSV contains one row per chart interval and one column per chart series. In **Total** mode it contains paid and refunded values, plus the previous-year paid series if enabled. In **Per document** mode it contains the displayed document series, subject to the 10-document limit. It uses semicolons as separators.

Use [Orders → Export](/orders-management#export-orders) to download individual order records instead of grouped chart values. For a guide to the other sales screens, see [Dashboard and Sales Charts](/orders-management/dashboard-and-sales-charts).
