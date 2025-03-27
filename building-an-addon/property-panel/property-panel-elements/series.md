# Series

{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (21).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "Series",
    "properties": {
        "labelName": "Data",
        "nameSuffix": "Series"
        "noun": "Series",
        "bindingPropertyName": "data"
    },
    "template": [
        {
            "type": "InputBox",
            "properties": {
                "labelName": "Name:",
                "allowBinding": true,
                "allowManualEntry": true,
                "bindingPropertyName": "id"
            }
        },
        {
            "type": "InputBox",
            "properties": {
                "labelName": "Input Box 1:",
                "allowBinding": true,
                "allowManualEntry": false,
                "bindingPropertyName": "input1"
            }
        },
        {
            "type": "InputBox",
            "properties": {
                "labelName": "Input Box 2:",
                "allowBinding": true,
                "allowManualEntry": false,
                "bindingPropertyName": "input2"
            }
        },
        {
            "type": "ColorOpacityInput",
            "properties": {
                "labelName": "Color Input",
                "bindingPropertyName": "colorInput",
                "allowCheckbox": true,
                "hasOpacity": false
            }
        },
        {
            "type": "HR",
            "properties": {}
        },
        {
            "type": "Label",
            "properties": {
                "text": "Some Text here"
            }
        },
        {
            "type": "InputBox",
            "properties": {
                "labelName": "Input Box 3:",
                "allowBinding": true,
                "allowManualEntry": true,
                "bindingPropertyName": "input3"
            }
        },
        {
            "type": "HR",
            "properties": {}
        },
        {
            "type": "HTMLLabelElement",
            "properties": {
                "text": "Check boxes:"
            }
        },
        {
            "type": "Checkbox",
            "properties": {
                "labelName": "Check box 1",
                "bindingPropertyName": "checkbox1"
            }
        },
        {
            "type": "Checkbox",
            "properties": {
                "labelName": "Check box 2",
                "bindingPropertyName": "checkbox2"
            }
        }
    ],
    "templateState": {
        "id": "Series 1",
        "input1": "",
        "input2": "",
        "input3": ""
        "colorInput": {
            "color": [
                {
                    "color": "#5a5a5a",
                    "alpha": 1,
                    "ratio": 0
                }
            ],
            "enabled": true,
            "weight": 2
        },
        "checkbox1": true,
        "checkbox2": false
    }
}
```
{% endtab %}

{% tab title="State definition" %}
The property name needs to match the string specified in bindingPropertyName property. The value will be the default value to show in the input box.

```json
{
    "data": {
        "series": [
                {
                    "id": "Series 1",
                    "input1": "",
                    "input2": "",
                    "input3": ""
                    "colorInput": {
                        "color": [
                            {
                                "color": "#5a5a5a",
                                "alpha": 1,
                                "ratio": 0
                            }
                        ],
                        "enabled": true,
                        "weight": 2
                    },
                    "checkbox1": true,
                    "checkbox2": false
                }
            ]
        }
    }
```
{% endtab %}
{% endtabs %}

The series pseudo element allows for the end user to add values to an array in state.  There are three sections to a series.

<details>

<summary>Series root property definition</summary>

This is where you specify the array property from state and cosmetic properties such as name, noun etc

</details>

<details>

<summary>Series template definition (orange box in the image).</summary>

This is where you specify the template child elements to appear for each item in the series / array.  The template can contain any of the other property panel elements.

You will configure the template child property panel elements as normal, and the root property name and it's position index in the array will automatically be attached to the start of the bindingPropertyName for you.   For example:

If you have a series call data,  with a template child text input with a bindingPropertyName of "title".  Referencing that title property in code you will use data\[0].title&#x20;

For a more detailed example you can see the template section in the property panel json above

</details>

<details>

<summary>Series template state</summary>

With the series template definition you specify what property elements you want for each of the items added to your series array.   The series template state section is where you specify the state structure for these elements.

For a more detailed example you can see the templateState section in the property panel json above

</details>

## **Configurable properties**

<details>

<summary><strong>bindingPropertyName</strong></summary>

**string** - the parent property name from defaultState with which to connect to.

<mark style="color:red;">**mandatory**</mark>

</details>

<details>

<summary>labelName</summary>

The title to give the series creation and selection element in the property panel

</details>

<details>

<summary>nameSuffix</summary>

This is the name to appear next to the label on the property element.  The default value is "**series**".

</details>

<details>

<summary>noun</summary>

This is the name of the series to be created when the add series button is clicked.  The next number in sequence is added to the series on creation. Eg if there is already an item in the array called "Series 1" and the noun is "Series"  the next item created will be "Series 2"

</details>

![](<../../../.gitbook/assets/image (22).png>)

{% hint style="info" %}
Note in build 1.11.x it is not possible to have a series element as a child of another series element.  This functionality was added in build 1.12.x
{% endhint %}
