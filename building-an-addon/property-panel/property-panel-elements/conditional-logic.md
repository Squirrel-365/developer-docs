# Conditional Logic

{% tabs %}
{% tab title="Property JSON" %}
```json
{
    "type": "ConditionalBlock",
    "properties": {
        "bindingPropertyName": "type",
        "equals": "url"
    },
    "children": [
        {
            "type": "InputBox",
            "properties": {
                "labelName": "URL:",
                "allowBinding": true,
                "allowManualEntry": true,
                "spellcheck": false,
                "type": "URL",
                "liveUpdate": true,
                "bindingPropertyName": "url"
            }
        }
    ]
}
```
{% endtab %}
{% endtabs %}

This pseudo element is used conditionally show or hide other property panel elements based on a boolean check.  If the value in the "equals" property matches the value in the "bindingPropertyName" property then the children of the conditional block are show, otherwise they are hidden

## **Configurable properties**

<details>

<summary><strong>bindingPropertyName</strong></summary>

**string** - the parent property name from defaultState with which to connect to.

<mark style="color:red;">**mandatory**</mark>

</details>

<details>

<summary>equals</summary>

The value from state to compare against the value in the bindingPropertyName property.

</details>

{% hint style="info" %}
Note in build 1.11.x it is not possible to have a conditional logic element as a child of a series element.  This functionality was added in build 1.12.x
{% endhint %}
