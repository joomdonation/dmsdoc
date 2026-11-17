---
title: 'Validate Field Data - Client Side'
media_order: client_side_validation.png
taxonomy:
    category:
        - docs
---

**Documents Seller** uses [jQuery Validation Engine](http://posabsolute.github.io/jQuery-Validation-Engine/) for client side validation. If you setup **Validation Rules** for a field, as soon as you enter data for that field, the engine will validate the data you entered with the configured rules and if it's not valid, an error message will be shown to let you know about the error and correct it.

If you want to validate data of a custom field using this custom field, go to Documents Seller -> Custom Fields, click on a custom field to edit, enter the rules you want to use into **Validation Rules** setting of that custom field. For example:

- **validate[required,custom[email]]** will make the field required and must be a valid email
- **validate[required,custom[integer],min[10]]** will make the field required and the must be an integer smaller than 10

See [http://posabsolute.github.io/jQuery-Validation-Engine/#validators](http://posabsolute.github.io/jQuery-Validation-Engine/#validators) for list of validators supported by this library and use the one meets your need

To help you configure it easier, the system tries to populate **Validation Rules** automatically base on two settings in custom fields:
- **Required**: If you select Yes, the system will insert **validate[required]** to **Validation Rules** automatically.
- **Date type vailidation**: When you select an option, the system will insert the related rules into **Validation Rules** automatically. For example, when you select **Min integer**, the system will insert **validate[required,custom[integer],min[-5]]**, of curse, you will need to change -5 to the correct value you want.

![Client Side Validation Settings](client_side_validation.png)