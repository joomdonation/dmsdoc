---
title: 'Offline Payment'
media_order: 'os_osm_offline_cash.zip,os_osm_offline_cheque.zip'
taxonomy:
    category:
        - docs
visible: true
---

**Offline payment** plugin is a special payment plugin comes with the extension. It allows customers to make payment for the order later (not at the time they purchase your documents) by bank transfer, by cash...

When customers choose offline payment for the order, the system will mark the order status as **Pending**. It will also display a message which guide users how to make payment.... This guide will also be sent to them via email

After receiving payment from customer for the order, admin will login to backend of the site, click on the order record, change the status from **Pending** to **Paid**. At that time, the user will receive a confirmation email from the system contains the purchase document. If he has user account, he can login, access to Orders History page to download the purchased documents from there.

If you use **Offline Payment** on your site, please go to **Documents Seller** => **Messages**, find and change the following messages to meet your need (mostly guide users how to send payment to you)

- Offline payment Email Subject
- Offline payment Email Body
- Order activated Email Subject
- Order Activated Email Body
- Thank You Message (Offline Payment)