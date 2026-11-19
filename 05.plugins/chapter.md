---
title: Plugins
taxonomy:
    category: docs
---

The Documents Seller package includes plugins for storefront content, integrations, and maintenance. Manage them in **System → Manage → Plugins** in the Joomla administrator. Configure [payment plugins](/setup/payment-plugins) in **Documents Seller → Payment Plugins**.

| Plugin | When to use it |
| --- | --- |
| [Content - DMS Category](/plugins/content-dms-category) | Display a category's documents inside a Joomla article, such as a product guide or landing page. |
| [Documents Seller - AcyMailing](/newsletter-integrations/acymailing) | Add customers to default or document-specific mailing lists when their orders are confirmed. |
| [Documents Seller - Mailchimp](/newsletter-integrations/mailchimp) | Add customers to document-specific audiences, groups, and tags when their orders are confirmed. |
| [Documents Seller - Joomla Users](/setup/custom-fields/automatic-checkout-field-population#use-joomla-user-data) | Prefill checkout fields with information stored in a signed-in customer's Joomla account. |
| [Documents Seller - Community Builder](/setup/custom-fields/automatic-checkout-field-population#use-community-builder-profiles) | Prefill checkout fields with information stored in a signed-in customer's Community Builder profile. |
| [Smart Search - Documents Seller](/plugins/smart-search) | Let visitors find documents alongside other site content in Joomla Smart Search. |
| [Task - DMS House Keeping](/plugins/scheduled-maintenance) | Use Joomla Scheduled Tasks to clean up old invoice PDFs and abandoned online payment orders. |

See [Newsletter Integrations](/newsletter-integrations) for an overview of subscribing customers after a purchase, or [Automatic Checkout Field Population](/setup/custom-fields/automatic-checkout-field-population) to configure profile field mappings.

Keep **Documents Seller - System (DO NOT UNPUBLISH)** enabled for core store operations, including [deferred account creation](/getting-started/configuration/checkout-and-accounts#customer-accounts-and-checkout-fields) and coupon usage updates. **Installer - Documents Seller** handles [Joomla Update](/getting-started/installation#use-joomla-update) for the extension.
