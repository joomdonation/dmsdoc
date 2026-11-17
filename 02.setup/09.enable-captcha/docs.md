---
title: 'Enable Captcha'
taxonomy:
    category:
        - docs
---

If you want to enable Captcha to protect order form in **Documents Seller** from spams, please follow the instructions below:

1. Configure your site to use recaptcha, see instructions from Joomla documentation at [https://docs.joomla.org/J3.x:Google_ReCaptcha](https://docs.joomla.org/J3.x:Google_ReCaptcha)
2. Go to Documents Seller -> Configuration, look at **Enable Captch** config option and change it to one of the following value:
* **Yes**: The system will show captcha protection on order form for both Public and Logged in users.
* **Only for public users**: The system will only show captcha on order form for Public users (who is not having account or not logged in only) only.