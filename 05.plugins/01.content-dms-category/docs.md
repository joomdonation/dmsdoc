---
title: 'Content - DMS Category'
media_order: assign_ticket.png
taxonomy:
    category:
        - docs
---

Use **Content - DMS Category** to display a list of documents inside a Joomla article. For example, you can introduce a collection of templates in an article and place the related downloads immediately below the introduction.

## Embed a category in an article

1. In the Joomla administrator, go to **System → Manage → Plugins**, enable **Content - DMS Category**, and save.
2. Go to **Documents Seller → Categories** and find the category's numeric **ID**.
3. Open the article under **Content → Articles**. Insert `{dmscategory ID_OF_CATEGORY}` where the listing should appear. For example, enter `{dmscategory 12}` to display the documents in category 12.
4. Save the article and open it on the frontend to verify the listing.

## Control the listing

The plugin uses the category's **Category Layout** setting for **Default**, **Columns**, and **Table**. If the category is set to **Grid**, the embedded listing uses **Default**. The article displays the full list of matching published documents on one page.

If you enable **Show Documents From Children Categories** in **Documents Seller → Configuration → General**, the listing also includes documents from published subcategories. See [Categories](/setup/categories) for category setup.
