---
title: 'Scheduled Maintenance'
taxonomy:
    category:
        - docs
---

Use **Task - DMS House Keeping** to schedule Documents Seller cleanup in Joomla.

| Task type | What it removes |
| --- | --- |
| **Documents Seller - Delete Old Invoices** | Generated invoice PDF files last modified more than 24 hours ago. The order records and invoice numbers remain available, and Documents Seller regenerates the PDF when someone requests the invoice. |
| **Documents Seller - Delete Incomplete Payment Orders** | Pending orders using online payment methods, along with their items and saved custom field values. Paid and refunded orders and pending offline orders are retained. **Days to delete incomplete payment orders after** defaults to `20` and accepts values of `5` or more. Choose a delay that leaves enough time for online payments to be confirmed. |

## Schedule a cleanup task

1. Go to **System → Manage → Plugins** and enable **Task - DMS House Keeping**.
2. Go to **System → Manage → Scheduled Tasks**, click **New**, and choose the task type.
3. Enter a title and choose an **Execution Rule** and its timing. For incomplete orders, enter the number of days to keep them. Set **Status** to **Enabled** and save.
4. Check the task's **Last Run Date** and result after it runs. If it does not run as expected, check which scheduler starts your tasks. See Joomla's [How to Choose a Scheduler](https://guide.joomla.org/user-guide/scheduled-tasks/how-to-choose-a-scheduler).

To review the pending orders before scheduling cleanup, open [Orders Management](/orders-management#find-and-edit-orders) and set **Select State** to **Unpublished**. This view includes pending offline orders, which the cleanup task retains.
