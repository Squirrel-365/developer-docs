# Input Box

{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (16).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "InputBox",
    "properties": {
        "labelName": "Button Text:",
        "shortPropertyName": "",
        "disabled": false,
        "type": "Text",
        "min": 0,
        "max": 0,
        "step": 1,
        "allowBinding": true,
        "allowCounter": false,
        "allowManualEntry": true,
        "spellcheck": false,
        "placeholder": "",
        "textArea": false,
        "textAreaRows": 5,
        "liveUpdate": false,
        "bindingPropertyName": "buttonText"
    }
}
```
{% endtab %}

{% tab title="State definition" %}
The property name needs to match the string specified in bindingPropertyName property. The value will be the default value to show in the input box.

```json
{
    "buttonText": "Get Data"
}
```
{% endtab %}
{% endtabs %}

This element has a large number of configurable properties. If a property has a default value then you do not need to provide it in the propertyPanel.json file unless you want to specify a value different to the default.

## **Configurable properties**

<details>

<summary><strong>bindingPropertyName</strong></summary>

**string** - the property name from defaultState with which to connect to.

<mark style="color:red;">**mandatory**</mark>

</details>

<details>

<summary><strong>labelName</strong></summary>

**string** - the text to display above the input box as a title

<mark style="color:red;">**mandatory**</mark>

</details>

<details>

<summary><strong>shortPropertyName</strong></summary>

**string** - the text to display inside and on the right of the text input box.

defaults to an empty string

</details>

<details>

<summary><strong>disabled</strong></summary>

**bool** - if set to true this will disable the input box for interaction

defaults to false

</details>

<details>

<summary><strong>type</strong></summary>

**string** ( Text | Integer | Decimal | Currency | Percent | Password | URL )

defaults to Text

</details>

<details>

<summary><strong>min</strong></summary>

**number** - the minimum value allowed to be entered

For Integer, Decimal, Currency and Percent types

defaults to 0

</details>

<details>

<summary>max</summary>

**number** - the maximum value allowed to be entered

For Integer, Decimal, Currency and Percent types

defaults to 0

</details>

<details>

<summary>step</summary>

**number** - the size of increments a number increases in when using allowCounter

For Integer, Decimal, Currency and Percent types

defaults to 0

</details>

<details>

<summary>allowBinding</summary>

**bool** - specifies whether you want the input field to be bindable or not

defaults to true

</details>

<details>

<summary>allowManualEntry</summary>

**bool** - specifies whether you want people to be able to type values into the input box

defaults to true

</details>

<details>

<summary>allowCounter</summary>

**bool** - specifies whether to add up and down stepper arrows to the input box

For Integer, Decimal, Currency and Percent types

defaults to false

</details>

<details>

<summary>spellcheck</summary>

**bool** - specifies whether you want the browser to highlight incorrect spelling in text within the text input box

defaults to true

</details>

<details>

<summary>placeholder</summary>

**string** - what placeholder text to display in the empty input box

defaults to empty string

</details>

<details>

<summary>textArea</summary>

**bool** - specifies whether the input box is a single line text input, or a multi-line text area input

defaults to false

</details>

<details>

<summary>textAreaRows</summary>

**number** - specifies how many rows tall to make the text area input

defaults to 5

</details>

<details>

<summary>liveUpdate</summary>

**bool** - specifies whether you want each key press in the input box to trigger an update in state.  Note this will trigger communication to the addon for each key press

defaults to false

</details>

