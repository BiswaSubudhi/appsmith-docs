# Capturing Data (Write)

This document presumes you have successfully [connected to a data source](../../connecting-to-data-sources/) and have a [Query](broken-reference/) that can insert/update/delete data. You should also have gone through the basics of [using widgets](../displaying-data-read/#widgets).

The following widgets can be used to capture user inputs in an application

* [Checkbox](../../../reference/widgets/checkbox.md)
* [Datepicker](../../../reference/widgets/datepicker.md)
* [Filepicker](../../../reference/widgets/filepicker.md)
* [Form](../../../reference/widgets/form.md)
* [Input](../../../reference/widgets/input.md)
* [Maps](../../../reference/widgets/maps.md)
* [Radio Group](../../../reference/widgets/radio-group.md)
* [Rich Text Editor](../../../reference/widgets/rich-text-editor.md)
* [Select](../../../reference/widgets/dropdown-1.md)
* [Switch](../../../reference/widgets/switch.md)

Widgets store their user input in an internal property that can be referenced using javascript.

### Example SQL

```sql
INSERT INTO users ("name", "createdAt", "gender")
  VALUES ({{nameInput.text}}, {{moment().format("YYYY-MM-DD")}}, 
  {{genderDropdown.selectedOptionValue}});
```

**Example Post Body**

```sql
{
  "name": {{nameInput.text}},
  "createdDate": {{moment().format('YYYY-MM-DD')}},
  "gender": {{genderDropdown.selectedOptionValue}}
}
```

In the examples above, **`text`** is the internal property of the **`nameInput`** widget while **`selectedOptionValue`** is the internal property of the **`genderDropdown`** widget. The **`createdDate`** key is populated with the value of the current date using the `moment.js` library

## Triggering Updates

Since write operations are more expensive, the Query should be triggered once all the user data is captured. To do this, we can make use of a [Button](../../../reference/widgets/button/) widget and configure the [Query](../querying-a-database/) to run in the onClick of the [button](../../../reference/widgets/button/).

The property pane has an action section where all the interactions that a user can perform with a widget are listed. We can configure the action to be taken when the interaction takes place in this section.

To [configure the Query](../querying-a-database/) we want to call when a button is clicked, we can select the action in the onClick dropdown.

![](<../../../.gitbook/assets/button-onclick (2) (4) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (3) (5) (1) (1) (1) (2) (1) (1) (1) (1) (1) (3) (2) (2) (10).gif>)
