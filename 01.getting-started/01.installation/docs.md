---
title: Installation
taxonomy:
    category:
        - docs
---

Documents Seller 7.4.1 requires Joomla 4.4 or later and PHP 7.4 or later. Your Joomla version may require a newer version of PHP.

## Installation

1. Download the Documents Seller package, `com_dms.zip`, from [My Downloads](https://joomdonation.com/my-downloads.html) in your JoomDonation account. Keep the package intact so Joomla can install the component and its bundled modules and plugins together.
2. Sign in to the Joomla administrator with a Super User account and go to **System → Install → Extensions**.
3. On **Upload Package File**, select the `com_dms.zip` package. Joomla starts the upload and installation automatically.
4. After Joomla confirms the installation, open **Components → Documents Seller** to access the administrator dashboard.

Follow [Quick Start](/getting-started/quick-start) to publish a product and test the purchase and download flow.

## Upgrade

Back up your Joomla site files and database before updating. Install the new version over the existing version to keep your store data.

### Use Joomla Update
1. Sign in to your JoomDonation account and copy the Download ID for this site from [Download IDs](https://joomdonation.com/download-ids.html). Use a separate ID for each site. You can use the same ID for all your JoomDonation extensions on that site.
2. In the Joomla administrator, go to **Documents Seller → Configuration → General**. Paste the ID into **Download ID** and save.
3. Go to **System → Manage → Plugins** and make sure **Installer - Documents Seller** is enabled.
4. When an update is available, go to **System → Update → Extensions**, select the Documents Seller update, and click **Update**.

### Update Manually
Download the latest package from [My Downloads](https://joomdonation.com/my-downloads.html) and upload it using the [installation steps](#installation).

## Uninstall
1. In the Joomla administrator, go to **System → Manage → Extensions**.
2. Find and select **Documents Seller Package**, then click **Uninstall**. Joomla removes the component and the extensions installed with the package.

Uninstalling leaves the Documents Seller database tables in place so a future installation can reuse them. To permanently remove the store data, back up the database and remove the tables that start with your Joomla database prefix followed by `dms_`, such as `abc_dms_orders`. This also removes the stored orders and configuration.

## Move data from one site to a new site
If you are moving the store to a separate Joomla site, back up both sites first. Plan for the database records, downloadable files, and Joomla settings together.

1. Install Documents Seller on the new site. Export the Documents Seller tables from the old database using a tool such as phpMyAdmin. Import them into the destination database, replacing the empty Documents Seller tables from the new installation. If the sites use different database prefixes, update the table names in the SQL export before importing.
2. Copy the downloadable files to the new server, keeping their names and relative paths. Set **Documents Path** to the absolute path on the new server. Copy any category and document images the listings reference.
3. Check that orders and access levels reference the intended Joomla users and viewing access levels on the new site. Recreate the storefront menu items and install any separately purchased payment plugins the store uses.
4. Test checkout, email delivery, and access to an existing purchase on the new site.
