---
title: 'Taxes and Invoices'
taxonomy:
    category:
        - docs
---

Go to **Documents Seller → Configuration** to set the tax rate used at checkout and configure customer invoices.

## Flat-rate tax

- On **General**, enter **Tax Rate** as a percentage, such as `10` for 10% or `0` for no flat-rate tax. Documents Seller applies this rate to the order subtotal after discounts when EU tax rules are inactive. A new installation starts with a **Tax Rate** of `10`, so review it before taking orders.
- **Show Price Including Tax** adds the configured **Tax Rate** to the prices shown in document listings and on document details pages. With **No**, these pages show the price before tax. When EU tax rules are active, checkout still calculates the final tax using the customer's country and VAT number.

## EU Tax Rules

1. On **General**, set **Default Country** to your EU home country.
2. In [Custom Fields](/setup/custom-fields), publish the **Country** field so customers can select their billing country. Create and publish an optional **Text** field to collect VAT numbers. Make it available on every checkout form where customers should be able to enter a VAT number.
3. On **EU Tax Rules**, select that field in **VAT Number Field**. Saving an EU **Default Country** together with this field activates EU tax calculations at checkout. Clear **VAT Number Field** to return to the flat **Tax Rate**.
4. Under **EU VAT Number Validation Provider**, leave **European Union Webservice** selected to use it first. Documents Seller falls back to **vatcomply.com API** if the first service cannot return a result. Select **vatcomply.com API** to use it directly.
5. Set **Hide VAT Number Field For Home Country** to **Yes** if you want to hide the field for customers who select your home country. Documents Seller applies the home-country rate even when a domestic customer enters a valid VAT number.

With these rules active, Documents Seller uses the selected EU country's rate when the customer leaves the VAT number blank. It applies a zero rate for customers in another EU country with a valid VAT number and for customers outside the EU.

## Invoice Settings

- Set **Activate Invoice Feature** to **Yes** to generate PDF invoices for orders with an amount to pay. Documents Seller attaches available invoices to customer order emails. Signed-in customers can also download invoices for their paid purchases from [Orders History](/frontend-menu-options/orders-history).
- **Invoice Prefix** adds text before the number. It supports `[YEAR]`, `[MONTH]`, and `[YEAR_LAST_2_DIGITS]` in the prefix. **Invoice Start Number** sets the first number in a new sequence. **Invoice Number Length** pads the numeric part with leading zeros. For example, a prefix of `INV-`, a start number of `100`, and a length of `5` produce `INV-00100` as the first number.
- **Reset Invoice Number Every Year** starts a new numeric sequence each year. Include `[YEAR]` in **Invoice Prefix** if you want the year to distinguish invoices that have the same numeric part.
- **Invoice Format** is the PDF's HTML template. Replace the sample business details and logo with your own, and keep the placeholders you need, such as `[INVOICE_NUMBER]`, `[INVOICE_DATE]`, and `[ORDER_ITEMS]`.
- **PDF CSS** appears when **Documents Seller - MPDF** is enabled. Use it to style PDF invoices.
