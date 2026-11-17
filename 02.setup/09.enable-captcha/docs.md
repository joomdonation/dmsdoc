---
title: 'Enable Captcha'
taxonomy:
    category:
        - docs
---

Documents Seller uses the CAPTCHA plugin you select in Joomla to help reduce spam orders. CAPTCHA applies to guests and signed-in customers on the frontend checkout form, with or without the shopping cart.

## Set up CAPTCHA

1. Choose a CAPTCHA plugin for your Joomla version and install it if needed.
2. In the Joomla administrator, go to **System → Manage → Plugins** and open your CAPTCHA plugin. Configure its settings, set **Status** to **Enabled**, and save. If your plugin uses an external CAPTCHA service, follow the provider's instructions to enter the keys for your site.
3. Go to **System → Global Configuration → Site**, select the plugin under **Default Captcha**, and save.
4. Go to **Documents Seller → Configuration → General**, set **Enable Captcha** to **Yes**, and save.

## Test checkout

1. Open a purchasable document on the frontend and proceed to checkout. Test as a signed-in customer and, if your store allows guest purchases, in a private browser window as a guest.
2. If your plugin asks customers to enter an answer, submit the completed order form with an incorrect CAPTCHA answer. Confirm that checkout rejects the submission.
3. Submit a test order. Complete the CAPTCHA if prompted, or let the plugin verify the submission in the background. Confirm that checkout proceeds to payment or accepts the order, depending on your payment method.

## Troubleshoot CAPTCHA

- If **Default Captcha** does not list your plugin, check that it is installed and enabled under **System → Manage → Plugins**.
- If CAPTCHA is missing from checkout when you expect a visible challenge, check that you selected an enabled plugin in **Default Captcha** and set **Enable Captcha** to **Yes** in Documents Seller.
- If verification fails during a test order, check the plugin's settings and any required keys for your site. If you use a checkout template override, confirm that it includes the CAPTCHA field and test again.
