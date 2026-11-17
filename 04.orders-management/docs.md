---
title: 'Orders Management'
media_order: orders-management.png
taxonomy:
    category:
        - docs
---

In the Joomla administrator, go to **Documents Seller → Orders** to find customer orders, record payments received outside checkout, and manage access to purchased documents. Open an order to edit it or issue a refund. Use the list toolbar to email customers or export order data.

Use the [Sales Report](#sales-report) to compare products in a selected period. See [Dashboard and Sales Charts](/orders-management/dashboard-and-sales-charts) for sales trends and store totals, or [Scheduled Maintenance](/plugins/scheduled-maintenance) to clean up abandoned online payment orders.

![Orders Management](orders-management.png)

## Find and edit orders

- Search by first name, last name, email address, Joomla username, or transaction ID. Enter `id:123` to find order `123` or `user_id:42` to find orders linked to Joomla user `42`.
- Use **Select document** to find orders that contain a particular published document.
- By default, the list shows paid and refunded orders and pending offline orders. In **Select State**, choose **Published** for paid orders or **Unpublished** for pending orders, including incomplete online payments.
- Click the customer's first name to open an order. If invoicing is enabled, click the number in the **Invoice** column to download the PDF for an order with a positive amount and an invoice number. See [Taxes and Invoices](/getting-started/configuration/taxes-and-invoices).

## Add New Order

Create an order manually when a customer pays outside your site, such as by bank transfer without placing an order at checkout. The form records the payment details you enter.

1. On the **Orders** page, click **New**.
2. Under **Billing Information**, select an existing Joomla account in **User ID** if you want to link the order to that customer. The selection fills in the name and email fields that are blank. Review the billing details and enter any remaining information.
3. Under **Order Information**, select the purchased document and the **Payment Method**. You can select multiple documents when the shopping cart is enabled. The selectors list published documents and payment plugins.
4. Enter the **Total Amount** before discounts and tax, any **Discount**, and the **Tax Amount** if the field is shown. On save, Documents Seller subtracts the discount and adds the tax to calculate the order amount. Enter the **Transaction ID** and adjust the **Payment Date** if you have those details.
5. Set **Order Status** to **Paid** if you have received the payment or **Pending** if you are still waiting for it. Click **Save & Close**.

Creating an order with **Paid** status sends the corresponding customer confirmation email if its subject is configured.

![Add New Order](add-new-order.png)

## Publish/Approve Order

After you receive payment for a [pending offline order](/setup/payment-plugins/offline-payment), mark it as paid in one of these ways.

- Select the order on the **Orders** page and click **Publish**, or click its unpublished icon in the **Order Status** column.
- Open the order, update the **Transaction ID** and **Payment Date** if needed, set **Order Status** to **Paid**, and save.

When a pending order becomes paid, Documents Seller sends the **Order Approved Email** if its subject is configured. It can include download links or attach the purchased files according to your [delivery settings](/getting-started/configuration/files-downloads-and-emails). Customers can also retrieve eligible downloads through a published [Orders History](/frontend-menu-options/orders-history) menu item after signing in.

Use **Unpublish** to return a selected order to **Pending** and suspend access to its downloads. **Delete** removes the selected orders and their items from Documents Seller. Use the [Refund](#refund-an-order) action to send money back through a supported payment gateway.

## Refund an order

Open the order, click **Refund** in the toolbar, and confirm. The action submits a refund for the order to its payment gateway. For refunds made directly in the gateway or through another channel, you can record the outcome by setting **Order Status** to **Refunded** and saving the order.

The **Refund** button is available for paid orders with a positive amount and a **Transaction ID**. Your Joomla account needs the **Configure ACL & Options** permission for Documents Seller, and the order's payment plugin must be published and configured to support refunds. For example, the [PayPal](/setup/payment-plugins/paypal#enable-refunds-from-orders) plugin needs API credentials for the selected environment. The [Authorize.Net](/setup/payment-plugins/authorize-net) plugin uses its **API Login** and **Transaction Key**.

After a successful refund through the toolbar, Documents Seller sets the order to **Refunded** and sends the **Order Refunded Email** if its subject is configured. The order's download links stop working and its items disappear from the customer's **Orders History**. Verify that the order shows **Refunded** after the action. If it still shows **Paid**, check the gateway's transaction record before retrying.

## Resend Email

Select one or more orders and click **Resend Email** to send the customer email again. Documents Seller uses the current template for the order. It sends the free download confirmation for orders containing only free documents, the offline payment email for pending orders containing a paid document, and the order confirmation for paid orders containing a paid document. Administrator notifications are omitted. See [Emails & Messages](/setup/emails-messages) to edit the templates.

For a follow-up about a refunded order, use **Batch Mail**. **Resend Email** can send the standard order confirmation for a refunded order.

## Batch Mail

Use **Batch Mail** to send a custom message about selected orders, such as letting buyers know that an updated file is available.

1. Filter the **Orders** list if needed, then select the orders to email.
2. Click **Batch Mail** and fill in both **Subject** and **Message**.
3. Use tags such as `[FIRST_NAME]`, `[LAST_NAME]`, and `[EMAIL]` in either field to personalize the message. Use `[ITEM_NAME]` for the first document name or `[ORDER_DETAIL]` in the message body for the full order summary. See [Order tags](/setup/emails-messages#order-tags).
4. Click **Process** to send the email.

Documents Seller sends one message per selected order to the email address saved on that order and skips invalid addresses. A customer with multiple selected orders can receive multiple messages.

## Export orders

Apply any search, document, or state filters on the **Orders** page, then click **Export** to download `order_list.csv`. The file contains one row per matching order across all pages, regardless of which rows you select. Orders are sorted by ID in descending order.

The CSV includes the core billing fields, document names, subtotal, discount, final amount, order date, order status, transaction ID, and order ID. **Tax Amount** appears when the configured **Tax Rate** is greater than zero. The export omits extra custom fields.

The CSV labels both paid and refunded orders as **Paid**. Set **Select State** to **Published** before exporting if you want only orders that are currently paid.

## Sales Report

Go to **Documents Seller → Sales Report** and choose a reporting period. The available periods are **Today**, **Yesterday**, **This Week**, **Last Week**, **Last 7 Days**, **This Month**, **Last Month**, **Last 30 Days**, **This Year**, and **Last Year**. The report uses the order creation date.

The report shows each published document with sales in the chosen period. **#Sales** counts the order items for that document, **Income** adds up the prices recorded on those items, and **# New Customers** counts the orders flagged as coming from new customers. An order with multiple documents can contribute to more than one product row.

The report includes paid orders and pending offline orders, and excludes refunded orders. **Income** reflects item prices before order-level discounts and tax. Use the [order export](#export-orders) if you need the amounts recorded on individual orders.

![Sales Report](sales-report.png)
