---
title: 'Automatic Checkout Field Population'
taxonomy:
    category: docs
---

Automatically fill checkout fields with information already stored in a signed-in customer's account. This saves customers from entering details such as their company, phone number, or address again.

Use one of the following plugins, depending on where you store customer information:

| Plugin | Source data |
| --- | --- |
| **Documents Seller - Joomla User Custom Fields** | Published Joomla user custom fields. The mapping selector also offers the account's `username`, `name` (full name), and `email`. |
| **Documents Seller - Community Builder** | Fields stored in the customer's Community Builder profile. Community Builder must be installed and enabled. |

Both plugins use the **Fields mapping** setting in the Documents Seller custom field editor. The mapping connects a checkout field to the corresponding source field; the field names do not have to match.

## Use Joomla user data

1. In the Joomla administrator, go to **Users → Fields** and create or check the user custom fields you want to use. Ensure they are published.
2. Open a test user under **Users → Manage**, enter values in those custom fields, and save the account.
3. Go to **System → Manage → Plugins**, open **Documents Seller - Joomla User Custom Fields**, set **Status** to **Enabled**, and save.
4. [Map the checkout fields](#map-the-checkout-fields) to the corresponding Joomla fields.

Joomla user custom fields appear by their titles in the mapping selector. Use fields belonging to Joomla users; custom fields created for articles or other content are not offered.

For example, if you have a Joomla user custom field titled **Business Phone**, open the Documents Seller **Phone** field and select **Business Phone** in **Fields mapping**. The signed-in customer's saved phone number can then fill the checkout field.

## Use Community Builder profiles

1. Install and enable Community Builder. Create or check the profile fields you want to use, and save values in a test customer's profile.
2. In the Joomla administrator, go to **System → Manage → Plugins**, open **Documents Seller - Community Builder**, set **Status** to **Enabled**, and save.
3. [Map the checkout fields](#map-the-checkout-fields) to the corresponding Community Builder fields.

Community Builder fields appear by their stored field names, such as `cb_company` or `cb_phone` if you have created fields with those names. Select the actual field used on your site.

Enable the profile integration you intend to use. When several profile plugins are enabled, Documents Seller uses the first available set of mapping options and the first non-empty set of profile data. It does not combine Joomla and Community Builder fields into one source.

## Map the checkout fields

1. Go to **Documents Seller → Custom Fields** and open an existing checkout field, or [create a new field](/setup/custom-fields/add-new-custom-field).
2. In **Fields mapping**, select the source field containing the value you want to use.
3. Ensure that the checkout field is published and that its **Access** and **Document** settings allow it to appear for the customer and product you are testing.
4. Click **Save & Close** and repeat for each field you want to populate.

For example, a site using Community Builder could configure these mappings:

| Documents Seller checkout field | Community Builder source field |
| --- | --- |
| Company | `cb_company` |
| Phone | `cb_phone` |
| City | `cb_city` |

These source names are examples; use the names offered by your site's mapping selector. For lists, radio buttons, and checkboxes, make sure the source values match the choices configured in the checkout field. Choose compatible field types, especially for fields that can contain several selected values.

To remove a mapping, choose **Select Field** in **Fields mapping** and save.

## Test field population

1. Open a fresh private browser session and sign in to the frontend as the test customer whose profile contains the source values.
2. Add an appropriate document to the cart and open checkout.
3. Check that the mapped fields contain the expected values.
4. Change a value at checkout, complete a test order, and open it under **Documents Seller → Orders** to check the saved answer.

Customers can review and edit the populated values before submitting the order. Their checkout changes are saved with the order; these plugins do not update the Joomla account or Community Builder profile.

## Understand which values are used

Profile mapping applies to signed-in customers. Guests enter their information normally. Fields still follow their usual default values, validation, access, and document assignment settings.

If checkout is restoring previously entered information from the current session, it uses that information before loading profile data. This also preserves the customer's entries when they return after a validation error. Use a fresh browser session when testing a changed profile or mapping.

When a profile integration returns mapped data, Documents Seller uses that data instead of loading details from the customer's previous order. It does not fill the remaining fields from that order. If no integration returns data, checkout can reuse the signed-in customer's most recent order details. Checkout also supplies the Joomla account name and email when those checkout values have not already been set.

## Troubleshooting

- **Fields mapping is missing:** check that the intended integration plugin is enabled, then reopen the checkout field. For Joomla, check that the Fields component is enabled and your user custom fields are published. For Community Builder, check that the component is enabled and has eligible profile fields.
- **The expected source field is missing:** check that it belongs to Joomla users or the Community Builder profile, rather than another type of content. Also check whether another enabled profile plugin is supplying the mapping options.
- **A mapped value is blank or unexpected:** check the signed-in customer's saved profile, the selected mapping, and the checkout field's available choices. Retest in a fresh browser session.
- **The checkout field itself is missing:** check its publication status, access level, and document assignment. See [Custom Fields](/setup/custom-fields).
