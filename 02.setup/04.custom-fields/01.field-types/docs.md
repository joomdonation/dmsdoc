---
title: 'Supported Field Types'
taxonomy:
    category:
        - docs
---

Use **Field type** in the field editor to choose how customers enter information, select options, or read instructions at checkout.

| Field type | Use it for |
| --- | --- |
| **Text** | A single line of text, such as a domain name or purchase order number. |
| **Textarea** | Longer answers, such as order notes or special instructions. |
| **List** | A dropdown with one selection. Set **Multiple** to **Yes** to allow several selections. |
| **Checkboxes** | A visible list of options that customers can select independently. |
| **Radio** | A visible list of options with one selection. |
| **Date** | A calendar picker, for example to ask for a preferred support start date. |
| **Heading** | A section heading. Enter the heading in **Title**. |
| **Message** | Instructions or other text within the form. Enter the message in **Description**. |
| **Countries** | A dropdown populated from the Documents Seller country list. |
| **State** | A dropdown of states or provinces for the selected country. |
| **SQL** | A dropdown populated by a database query. Enter a `SELECT` query in **Default values** that returns a `value` column for the stored value and a `text` column for the displayed label. |
| **Url** | A web address, such as the customer's website. |
| **Email** | An additional email address, such as a billing contact. |
| **Tel** | A telephone number, such as a support contact's number. |

## Use the built-in Country and State fields together

The checkout form links the built-in **Country** and **State** fields. When a customer changes **Country**, the available **State** options update automatically. If **State** is shown without **Country**, it uses the country selected in **Default Country**. See [Checkout and Accounts](/getting-started/configuration/checkout-and-accounts).
