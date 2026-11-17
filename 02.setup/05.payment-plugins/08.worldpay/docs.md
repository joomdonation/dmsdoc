---
title: Worldpay
taxonomy:
    category:
        - docs
visible: true
---

Configure the payment response in your Worldpay merchant account.

1. Sign in to your Worldpay merchant account and edit the installation.
2. In **Payment Response URL**, enter the URL below. Replace `https://domain.com` with your site URL.

   ```text
   https://domain.com/index.php?option=com_dms&task=payment_confirm&payment_method=os_worldpay&notify=1
   ```

3. Select **Payment Response enabled**.
