---
title: 'Stripe Checkout'
taxonomy:
    category:
        - docs
visible: true
---

## Installation

Extract `os_dms_stripecheckout_unzip_first.zip` to find `os_dms_stripecheckout.zip`. Install `os_dms_stripecheckout.zip` from **Documents Seller → Payment Plugins**. See [Install New Payment Plugin](/setup/payment-plugins#install-new-payment-plugin).

## Configuration

1. Open the plugin and enter your Stripe API keys. See the [Stripe API keys documentation](https://stripe.com/docs/keys#api-keys).
2. Sign in to your Stripe account and add the webhook endpoint below. Replace `https://domain.com` with your site URL. See the [Stripe webhook setup instructions](https://stripe.com/docs/webhooks/setup#add-endpoint-dashboard).

   ```text
   https://domain.com/index.php?option=com_dms&task=payment_confirm&payment_method=os_stripecheckout
   ```

3. Select the `checkout.session.completed` event for the webhook.
4. In the webhook settings, click **Click to reveal** to get the signing secret. Enter it in **Signing Secret** in the plugin, then save and publish the plugin.
