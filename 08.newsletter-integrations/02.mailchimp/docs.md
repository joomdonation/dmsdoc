---
title: Mailchimp
taxonomy:
    category: docs
---

Use **Documents Seller - Mailchimp** to add customers to Mailchimp audiences and assign groups and tags when their orders are confirmed. Configure the selections for each document, so customers receive follow-up messages relevant to the products they buy.

## Prepare Mailchimp

In your Mailchimp account, create the audience you want to use and any groups or tags you want to assign. The document editor lets you select existing audiences, groups, and tags from that account.

Generate a Mailchimp Marketing API key:

1. Sign in to Mailchimp, open your profile menu, and choose **Profile**.
2. Open **Extras → API keys**, then click **Create A Key**.
3. Give the key a descriptive name, such as **Documents Seller**, and click **Generate Key**.
4. Copy the complete key when it is displayed. You cannot retrieve the complete key again later.

See Mailchimp's [About API Keys](https://mailchimp.com/help/about-api-keys/) guide for the current instructions. Keep the key private and update the plugin settings if you replace it or it expires.

## Enable the plugin

1. In the Joomla administrator, go to **System → Manage → Plugins** and open **Documents Seller - Mailchimp**.
2. Enter the key in **Mailchimp API Key**.
3. Set **Double Opt-in** to **Yes** if new contacts should confirm their subscription by email. Leave it set to **No** to subscribe new contacts directly.
4. Set **Status** to **Enabled** and click **Save & Close**.

Double opt-in applies to new contacts. Existing contacts keep their current subscription status; purchasing a document does not automatically resubscribe an unsubscribed contact.

## Configure a document

1. Go to **Documents Seller → Documents** and open the document.
2. Open the **Mailchimp Settings** tab.
3. Select the **Audiences**, **Groups**, and **Tags** you want to assign to customers who purchase this document.
4. Click **Save & Close**. Repeat for other documents that should use the integration.

| Setting | Effect |
| --- | --- |
| **Audiences** | Add the customer to each selected audience. |
| **Groups** | Assign the customer to the selected groups. Each option includes its audience and group category. Selecting a group also includes its audience, even if you do not select that audience separately. |
| **Tags** | Apply the selected tags. Each option includes its audience. Selecting a tag also includes its audience. |

For example, create a **Template Buyers** tag in your **Store Customers** audience and select that tag for a template document. When an order for the template is confirmed, the integration adds the customer to **Store Customers** and applies **Template Buyers**.

For a cart containing several documents, the plugin combines their audiences, groups, and tags. Repeated selections are applied once. It adds the selected groups and tags without removing other group memberships or tags from an existing contact.

Selections are made per document. To add buyers of every product to the same audience, select that audience, or one of its groups or tags, on each document. If a document has no selections, it contributes no Mailchimp subscriptions to the order.

## Test the integration

1. Configure a document and place a test order using an email address you can check.
2. Complete the online payment. For an offline payment, confirm receipt of payment, then open the order under **Documents Seller → Orders**, set **Order Status** to **Paid**, and save.
3. In Mailchimp, find the order's email address in the selected audience and check its groups and tags.
4. If **Double Opt-in** is enabled, use a new contact address and check for the confirmation email. The new contact remains **Pending** until the subscription is confirmed.

Orders with a zero total also trigger the integration when Documents Seller confirms them at checkout. Guest customers can be added because the integration uses the order's email address; a Joomla account is not required.

## Troubleshooting

- **The Mailchimp Settings tab is missing:** check that **Documents Seller - Mailchimp** is enabled.
- **Audiences, groups, or tags cannot be loaded:** check the API key and that it belongs to the account containing those selections. Confirm that your server can connect to Mailchimp. If loading fails, previously saved selections are kept.
- **A saved selection is marked Unavailable in Mailchimp:** check whether it was removed from Mailchimp or belongs to a different account. Choose a current option and save the document.
- **The order is paid but the contact is missing:** check the order's email address and the selections on its documents. With double opt-in, also look for a pending contact. Saving an already paid order does not trigger another subscription attempt; use a new test order after correcting the settings.

If the settings appear correct, check `dms_mailchimp.php` in the Joomla log folder, or ask your site administrator to check it. Failed subscription requests are logged with the order ID. A Mailchimp request failure does not stop the order from completing.
