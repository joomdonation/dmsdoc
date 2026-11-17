---
title: 'Software Update Download IDs'
taxonomy:
    category:
        - docs
---

If you sell software, your customers can use a Download ID to retrieve updates from your Documents Seller store. Use this workflow when an updater needs to fetch a package on the customer's behalf. For ordinary purchases, customers can use the download links in the order email or [Orders History](/frontend-menu-options/orders-history). To update Documents Seller itself, use the JoomDonation Download ID in the [installation guide](/getting-started/installation#use-joomla-update).

## Let customers manage their Download IDs

1. [Create a Joomla menu item](/frontend-menu-options#create-a-menu-item) of type **Documents Seller → Download Ids**. Give it a title such as `Manage Download IDs` and set **Access** to **Registered**.
2. Sign in as a customer who has a paid order. The order must match the customer's Joomla account or its email address. When that customer first opens the page, Documents Seller creates an ID if the account has none.
3. To get IDs for additional sites, the customer can select a number from 1 to 5 and click **Process**. The page shows the IDs and the associated domains. Under **Documents Seller → Messages**, use **Download IDs Manage Message** to tell customers where to enter the ID in your software.

## Connect your updater

1. Find the product's numeric ID in **Documents Seller → Documents**. To serve a separate update file, place it in the `updates` subfolder of **Documents Path** and select it in the document's [Update Package field](/setup/documents#offer-a-separate-software-update-package). Otherwise, the updater receives the product's standard download file.
2. Configure your updater to request `index.php?option=com_dms&task=download_update_package` on your store's HTTPS URL. Supply `document_id` for the purchased product, `download_id` for the customer's ID, and `domain` for the site installing the update. The request also accepts `dlid` in place of `download_id`.
3. Test with a customer who has bought the product. The store checks for a paid order containing that product and applies its **After X days** limit if configured. With the default domain validation, a successful request associates an unused ID with the supplied domain. Use a separate ID for each domain.

## Find or replace an ID

In the Joomla administrator, go to **Documents Seller → Download IDs**. Search by Download ID, domain, or Joomla username. A customer who moves to a different domain can generate a new ID and enter it in the updater. To revoke an ID, delete it from the list and have the customer replace it wherever it was in use.
