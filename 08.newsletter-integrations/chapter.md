---
title: 'Newsletter Integrations'
taxonomy:
    category: docs
---

Use newsletter integrations to add customers to mailing lists after Documents Seller confirms their orders. For example, customers who buy a template can join a list for template updates, while customers who buy an ebook can join a different list.

Choose the guide for the newsletter service you use:

| Guide | What you can configure |
| --- | --- |
| [AcyMailing](/newsletter-integrations/acymailing) | Subscribe customers to lists in AcyMailing on your Joomla site. Set default lists for all documents and additional lists for individual documents. |
| [Mailchimp](/newsletter-integrations/mailchimp) | Add customers to Mailchimp audiences and assign groups and tags selected for each document. |

## When customers are added

Both integrations use the email address entered on the order. They run when an online payment is confirmed, when you approve a pending offline order as **Paid**, or when Documents Seller confirms an order with a zero total at checkout. Placing an unpaid order alone does not subscribe the customer.

For a shopping cart order, the integration combines the selections from every document in the order. Configure the appropriate integration plugin and the document settings before placing a test order.

Newsletter integrations manage contacts in your chosen service. Configure and send your newsletters there. Documents Seller's [order emails](/setup/emails-messages), such as payment confirmations and download instructions, are configured separately.
