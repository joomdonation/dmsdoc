---
title: 'Files, Downloads, and Emails'
taxonomy:
    category:
        - docs
---

These options are on the **General** tab under **Documents Seller → Configuration**.

## File storage

- **Documents Path** is the absolute server path to the folder where Documents Seller looks for your files. By default, it is the `documents` folder in your Joomla site root. The folder must be writable for uploads through **Documents Seller → Files**. **Reset** fills in the default path. If you change the path, copy your existing files to the new folder with the same names and subfolders so existing documents can still find them.
- **Allowed File Types** lists the file extensions accepted by the file manager. Enter extensions without leading dots and separate them with `|`, as in `pdf|zip|docx`.

See [Upload Files](/setup/upload-files) for the available upload methods.

## Free downloads

1. Set **Download Free Documents** to the Joomla viewing access level you want to use for free downloads. Choose **Public** to offer them to guests, or **Registered** to ask visitors to sign in through the storefront before downloading.
2. Set **Collect User Information For Downloading Free Documents** to **Yes** to direct visitors to the order form before they receive the file. The information collected depends on your published [Custom Fields](/setup/custom-fields). Set it to **No** to offer a direct download from the storefront.
3. If visitors complete the form, set **Enable Instant Download Free Document** to **Yes** to start the download automatically on the completion page for an order containing only free documents.

## Deliver documents by email

- **Send Documents Via Email** attaches the files to the customer email once the order is confirmed. If your files are large, use download links to avoid email attachment size limits.
- **Send Download Link Via Email** adds links to the order details in the customer email once the order is confirmed. If you customize the email, keep the `[ORDER_DETAIL]` tag to include those links. See [Emails & Messages](/setup/emails-messages).
- **Download Link Valid In** sets the number of days a download-code link remains valid, measured from the order's payment or approval date. Leave it blank or enter `0` to disable this expiration. Download limits set on an individual [document](/setup/documents) still apply. Customers can also sign in and download eligible documents from [Orders History](/frontend-menu-options/orders-history) while those per-document limits allow it.

## Notification emails

- **Notification Emails** sets the recipients for administrator notifications. Separate multiple addresses with commas, as in `sales@example.com,orders@example.com`. In single-document checkout, a document's own notification addresses take precedence when configured.
- **Use Joomla Mail Template** wraps Documents Seller HTML emails in Joomla's global mail layout. This requires Joomla 5.2 or later with **Mail Template Layout** enabled in Joomla's **Mail Templates → Options**.
