---
title: 'Quick Start'
taxonomy:
    category:
        - docs
---

Set up one paid download and follow it from the storefront to the customer's inbox. This walkthrough uses a small sample PDF, one category, guest checkout, and the included Offline Payment method. Use a staging copy of your Joomla site and an email address you can check. You can complete the test without transferring money or connecting a payment gateway.

## 1. Install Documents Seller

Install the Documents Seller package in the Joomla administrator and open **Components → Documents Seller**. See [Installation](/getting-started/installation).

## 2. Set the currency, checkout, and delivery options

Go to **Documents Seller → Configuration → General** and check these settings.

| Setting | Value for this walkthrough |
| --- | --- |
| **Currency Code** and **Currency Symbol** | Set the currency you plan to sell in and its display symbol. |
| **Tax Rate** | Review the rate before testing. A new installation starts at `10` (10%). |
| **Purchase Documents** and **User Registration** | Select **Public** and **No** so you can place the test order as a guest. |
| **Activate Cart Feature** | Select **No** to go directly to checkout for one product. |
| **Documents Path** and **Allowed File Types** | Use a folder Joomla can write to and make sure `pdf` is allowed. |
| **Send Download Link Via Email** and **Send Documents Via Email** | Select **Yes** for the link and **No** for the attachment so you can test downloading the file from the email. |

Save your changes. Under **Documents Seller → Messages**, keep a subject and the `[ORDER_DETAIL]` tag in the **Order Approved Email** template so the approval email includes the order details and download link. See [Configuration](/getting-started/configuration) and [Emails & Messages](/setup/emails-messages).

## 3. Add your first product

1. Go to **Documents Seller → Files**, click **Upload Files**, and upload the sample PDF. See [Upload Files](/setup/upload-files).
2. Go to **Documents Seller → Categories**, click **New**, and enter `Guides` in **Name**. Set **Published** to **Yes** and **Access** to **Public**, then save. See [Categories](/setup/categories).
3. Go to **Documents Seller → Documents** and click **New**. Enter `Sample Guide` in **Title**, select **Guides** in **Category**, and select your PDF in **Choose File**. Enter a positive **Price**, such as `5.00` in your store currency. Set **Published** to **Yes** and **Access** to **Public**, then save. See [Documents](/setup/documents).

## 4. Enable a payment method and link to the catalog

1. In **Documents Seller → Payment Plugins**, open **os_offline**, set **Published** to **Yes** and **Access** to **Public**, then save. Unpublish any other payment methods you have yet to configure. See [Offline Payment](/setup/payment-plugins/offline-payment).
2. In Joomla, go to **Menus**, select a site menu, and click **New**. Enter `Shop` in **Title** and choose **Documents Seller → Category Default Layout** as the **Menu Item Type**. Set **Select Category** to **Guides**, set **Access** to **Public**, and save the menu item as published. See [Create a menu item](/frontend-menu-options#create-a-menu-item).

## 5. Place an order and download the file

1. Open the **Shop** page in a private browser window. Open **Sample Guide** and proceed to checkout. Check that the price, currency, and total are correct. Complete the form with your test email address and submit the order using **Offline Payment**.
2. In the Joomla administrator, go to **Documents Seller → Orders** and find your test order. Confirm that **Order Status** is **Pending**. Open the order, set **Order Status** to **Paid**, and save. See [Approve an order](/orders-management#publish-approve-order).
3. Open the approval email in the test inbox. Follow its download link in the private window and verify that it delivers the PDF you uploaded. If the email is missing, check the order status, the **Order Approved Email Subject**, and whether Joomla can send mail. If the email arrives without a link, check **Send Download Link Via Email** and `[ORDER_DETAIL]` in the approval email body. See [Files, Downloads, and Emails](/getting-started/configuration/files-downloads-and-emails).

## Before opening the store

- Configure the [payment methods](/setup/payment-plugins) you plan to offer and repeat the checkout and download test with each one. For online payments, use the gateway's test environment where available and confirm that the payment updates the order automatically. If you offer Offline Payment, add your payment instructions to the [customer messages](/setup/payment-plugins/offline-payment#set-up-offline-payments).
- Set the final [checkout and account options](/getting-started/configuration/checkout-and-accounts), [tax and invoice settings](/getting-started/configuration/taxes-and-invoices), and [delivery settings](/getting-started/configuration/files-downloads-and-emails). If customers will sign in to retrieve purchases, publish an [Orders History](/frontend-menu-options/orders-history) menu item and test it with a customer account.
- Publish the products you plan to sell. If you also offer free files, [configure and test the free download flow](/getting-started/configuration/files-downloads-and-emails#free-downloads).
