---
title: 'Documents Seller - AcyMailing'
taxonomy:
    category: docs
---

Use **Documents Seller - AcyMailing** to subscribe customers to mailing lists when Documents Seller confirms an order. You can use one list for all customers and add product-specific lists for follow-up messages, such as updates about a template they purchased.

## Enable the plugin

1. Install and enable AcyMailing on your Joomla site, then create the mailing lists you want to use.
2. In the Joomla administrator, go to **System → Manage → Plugins** and open **Documents Seller - AcyMailing**.
3. Set **Status** to **Enabled**. In **Default Mailing Lists**, select the lists that should apply to orders for any document. Leave this field empty if you only want to use document-specific lists. Save the plugin.

## Assign lists to a document

1. Go to **Documents Seller → Documents** and open the document you want to configure.
2. Open the **ACYMailing Settings** tab, select one or more lists in **Assign To Mailing Lists**, and save the document.
3. Repeat for any other document that needs its own mailing lists.

For each confirmed order, the plugin combines the **Default Mailing Lists** with the lists assigned to every document in the order. For example, if the default list is **Customers** and the order includes a document assigned to **Template Updates**, the customer is subscribed to both. If none of the settings specify a list, the plugin skips the order.

## Verify a subscription

Place a test order and complete the payment. For an offline payment, open the order in **Documents Seller → Orders**, set **Order Status** to **Paid**, and save after confirming receipt of payment. Orders with a zero total also qualify when Documents Seller confirms them at checkout.

In AcyMailing, search for the email address used on the order and check its list subscriptions. The plugin uses this address to find an existing contact or create one. If the **ACYMailing Settings** tab is missing from the document editor, check that both AcyMailing and the Documents Seller integration plugin are enabled.
