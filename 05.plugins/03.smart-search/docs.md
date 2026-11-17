---
title: 'Smart Search - Documents Seller'
taxonomy:
    category: docs
---

Use **Smart Search - Documents Seller** to include your downloadable products in Joomla Smart Search. It indexes the document title, short description, full description, and metadata. Search results link to the document detail page. If customers should be able to find a product by terms used inside the downloadable file, add those terms to the document's title or description in Documents Seller.

For a search form dedicated to the catalog, use the [DMS search module](/frontend-menu-options/modules#dms-search).

## Enable the plugin and index documents

1. In the Joomla administrator, go to **System → Manage → Plugins**, enable **Smart Search - Documents Seller**, and save.
2. Go to **Components → Smart Search** and click **Index**. After indexing finishes, look for your documents in the indexed content list under the **Documents** content type.
3. Use a **Smart Search** module or a menu item of type **Smart Search results** to make the search available on the frontend. If your site already uses Smart Search, you can use the existing search form.
4. Search for words from a published document's title or description on the frontend. Open the result and verify that it takes you to the document page.

## Keep search results up to date

Run **Index** again after adding or editing documents or changing their publication status or viewing access. If a deleted document still appears, find its entry in **Components → Smart Search**, select it, and click **Delete** to remove it from the index.

If a document is missing from frontend results, confirm that the document is published and that its **Access** level allows the test visitor to view it. When a document belongs to several categories, Smart Search groups it under the first of those categories in Documents Seller's category order. An unpublished first category can hide the document from search results. Review the category assignments and publication status, then run **Index** again.
