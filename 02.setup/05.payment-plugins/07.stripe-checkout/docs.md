---
title: 'Stripe Checkout'
taxonomy:
    category:
        - docs
visible: true
---

## Installation
When you purchase the payment plugin, you will receive a zip file called **os_dms_stripecheckout_unzip_first.zip**. Unzip that file, you will get the file os_dms_stripecheckout.zip. Go to Documents Seller -> Payment Plugins to install it as any other payment plugin. See [https://dmsdoc.joomservices.com/basic-setup/payment-plugins#install-new-payment-plugin](https://dmsdoc.joomservices.com/basic-setup/payment-plugins#install-new-payment-plugin) for installation instructions if needed.

## Configuration
1. Click on the payment plugin to edit, enter payment plugin parameters, then publish it

- For API Keys, you can follow instructions at https://stripe.com/docs/keys#api-keys to get it.
- For Signing Secret, you need to setup Webhook URL (see the next step) and get the information from there. In the webhook URL setting, click on "Click to reveal" button to get it 

2. You will need to login to your Stripe account, add a "Webhook URL" below (see https://stripe.com/docs/webhooks/setup#add-endpoint-dashboard for instructions)

https://domain.com/index.php?option=com_dms&task=payment_confirm&payment_method=os_stripecheckout

(Of course, need to replace https://domain.com/ with your website url)

Stripe will also asks you for the events for webhook, select event below:

checkout.session.completed