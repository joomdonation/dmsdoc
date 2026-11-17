---
title: 'Storefront Modules'
taxonomy:
    category:
        - docs
---

Documents Seller includes six Joomla site modules. Add them to template positions such as a sidebar, header, or home page section. You can publish several instances of a module with different settings, such as a latest-products list on the home page and a list for a single category on a landing page.

## Publish a module

1. In the Joomla administrator, go to **Content → Site Modules**. Open an existing module or click **New** and select one of the module types below.
2. Enter a title, select a **Position** offered by your site template, and set **Status** to **Published**. Choose an **Access** level that matches the intended audience.
3. Configure the module and use **Menu Assignment** to select the pages where it should appear. Click **Save & Close**.
4. Open one of those pages as a visitor and test the module and its links. If the module is missing, check its position, menu assignment, status, and access level.

See Joomla's [Site Modules guide](https://guide.joomla.org/user-guide/modules/modules-site-modules) for more on positions and assignments.

## DMS Cart

Show customers what they have added to their cart and give them a **Checkout** button. Enable **Activate Cart Feature** in [Checkout and Accounts](/getting-started/configuration/checkout-and-accounts#cart-and-purchase-access) first. In **Cart Type**, select **Mini cart** to show the item count or **Full cart** to show links to the individual documents. Test by adding an item from a page where the module appears and following its **Checkout** button.

## DMS Categories

Show links to published top-level categories the visitor can access. The list follows the ordering in **Documents Seller → Categories**. Set **Number Categories** to limit the list or leave it at `0` to show all eligible top-level categories. Use a [Categories List menu item](/frontend-menu-options/categories-list) when you want a full page of categories or a list of subcategories.

## DMS documents

Show a list of links to published documents the visitor can access. Use **Module type** to choose the order of the links.

| Module type | Sort order |
| --- | --- |
| **Latest Documents** | Most recently created first. |
| **Popular Documents** | Highest document hit counts first. |
| **Best sellers** | Most recorded order items first. The module counts order items across payment statuses. |

Set **Number of document** to the maximum number of links. In **Categories (comma seperated)**, enter numeric category IDs, such as `3,8`, or leave the field blank to include documents from any category. Find the IDs in **Documents Seller → Categories**.

## DMS search

Give visitors a keyword field and an optional category filter. The results page shows published documents the visitor can access. The search matches the entered text against the document's title, short description, or description. Use [Smart Search - Documents Seller](/plugins/smart-search) if you want to include documents alongside the rest of your Joomla content in a site-wide search.

## Tags modules for Documents Seller

Show the catalog's tags as a tag cloud. Add comma-separated tags in the **Tags** field when [editing a document](/setup/documents#describe-the-product). Clicking a tag opens the Documents Seller search results for that tag. **Max font size** and **Min font Size** set the upper and lower font sizes as percentages. Tags with more hits appear larger.

## Documents Seller View

Display the output of an existing Documents Seller menu item in a template position. For example, create a category menu item for featured products and display its grid in a home page section.

1. [Create and publish a Documents Seller menu item](/frontend-menu-options#create-a-menu-item) with the layout you want. To keep it out of the visible menu, set **Display in Menu** to **No** on its **Link Type** tab.
2. In the module, select that entry in **Menu Item**. Leave **Query String** blank to use the selected menu item's settings.
3. Test the module on its assigned page. Check that any product links open the expected pages.

## Set the menu context for module links

The cart, categories, documents, search, and tags modules offer an **Item ID** field. Start with it blank so Documents Seller can choose a menu context automatically. If links open with the wrong template or module assignments, try the numeric **ID** of an appropriate published Documents Seller menu item and verify the links again. A dedicated menu item for an individual document or category can take precedence when a link points to it.
