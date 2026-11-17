---
title: 'Checkout and Accounts'
taxonomy:
    category:
        - docs
---

Go to **Documents Seller → Configuration → General** to configure how customers place orders and create accounts.

## Cart and purchase access

- **Purchase Documents** sets the Joomla viewing access level used for paid purchases. Select **Public** to let guests reach checkout, or choose a more restrictive level if customers must sign in before ordering. The access level for free downloads is set separately. See [Files, Downloads, and Emails](/getting-started/configuration/files-downloads-and-emails).
- Set **Activate Cart Feature** to **Yes** to let customers buy several documents in one order. With **No**, customers go straight to checkout for one document at a time.
- **Checkout Form Layout** appears when the cart is enabled. Select **Default Layout** for the standard checkout or **Columns Layout** to display customer information and the order summary side by side on wider screens.
- Set **Enable Coupon** to **Yes** if you want customers to enter discount codes at checkout. Create the codes in [Coupons](/setup/coupons).

## Customer accounts and checkout fields

- **User Registration** adds required username and password fields to the order form for guests and gives existing customers a way to sign in. Customers with accounts can access their purchases later if you publish an [Orders History](/frontend-menu-options/orders-history) menu item.
- With **User Registration** enabled, set **Only Create User Account For Success Orders** to **Yes** to wait until the order is completed before creating the account. For offline payments, this happens when an administrator approves the order. With **No**, the account is created when the customer submits the order, before payment is completed. Keep **Documents Seller - System (DO NOT UNPUBLISH)** enabled for deferred account creation.
- **Default Country** preselects a country when checkout has no country value. It also identifies your home country for [EU Tax Rules](/getting-started/configuration/taxes-and-invoices).
- **Integration** can prefill mapped checkout fields for signed-in users from **Community Builder** or **JomSocial**. Each option appears when the corresponding extension is installed. Manage form fields and required information in [Custom Fields](/setup/custom-fields).

## Currency

- **Currency Code** sets the store currency used for payment processing. Choose a currency supported by your [payment plugins](/setup/payment-plugins).
- **Currency Symbol** and **Currency Position** control how prices are displayed, such as `€25.00` or `25.00€`. **Number Of Decimal**, **Decimal Point**, and **Thousands Separator** set the number format.

## CAPTCHA, terms, and privacy

- On **General**, set **Enable Captcha** to **Yes** to protect the order form. Configure and select an enabled Joomla CAPTCHA plugin first. See [Enable Captcha](/setup/enable-captcha).
- On **General**, set **Show Terms/Conditions Checkbox** to **Yes** and select a Joomla article in **Terms And Conditions Article**. The checkout form displays the checkbox when both settings are configured.
- On **Privacy Policy (GDPR) Settings**, set **Show Privacy Policy Checkbox** to **Yes** to add a required checkbox to the order form. Select a Joomla article in **Privacy Policy Article** or enter the policy page's URL in **Privacy URL**. If you fill in both fields, checkout uses **Privacy URL**.
