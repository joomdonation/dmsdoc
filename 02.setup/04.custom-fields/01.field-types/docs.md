---
title: 'Supported Field Types'
taxonomy:
    category:
        - docs
---

**Documents Seller** support the following custom field types:
1. **Textbox**  
2. **Textarea**
3. **List**: This field type will generate a dropdown (single or multiple select). To make it become multiple select, please set **Multiple** property to **Yes**
4. **Chekboxes**
5. **Radio**
6. **Date**: Display a calendar allows selecting a date
7. **Heading**: Display **title of the field** as a header on order form.
8. **Message**: Display a text message on order form. The message you want to display need to be entered into **Description** of the custom field.
9. **Countries**: Display list of published countries in a single dropdown select
10. **States**: Display list of states of a the selected country. When customers select a new country in the country dropdown, the list of states in this field will also be updated automatically

>>>>> Right now, we only allow one country field and one state field on the form so that it can work together (when country is changed, the states list will be changed / update, too).



>>>>> In case you don't have country field in the form but still have state field, the state field will get list of states from Default Country which you select in Configuration of Documents Seller
