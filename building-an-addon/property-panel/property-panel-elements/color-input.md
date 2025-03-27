---
description: Color picker with optional opacity
---

# Color Input

{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (18).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "ColorOpacityInput",
    "properties": {
        "labelName": "Button Color",
        "bindingPropertyName": "buttonColor",
        "allowCheckbox": false,
        "hasOpacity": false
    }
}
```
{% endtab %}

{% tab title="State definition" %}
The parent property name needs to match the string specified in bindingPropertyName property. In this example the parent property name is "buttonColor"

```json
{
    "buttonColor": {
        "type": "solid",
        "color": [
            {
                "color": "#22ee33",
                "alpha": 1,
                "ratio": 0
            }
        ],
        "rotation": 0,
        "enabled": true
    }
}
```
{% endtab %}
{% endtabs %}

This element has a number of configurable properties. If a property has a default value then you do not need to provide it in the propertyPanel.json file unless you want to specify a value different to the default.

{% hint style="info" %}
&#x20;Color is an array in preparation for supporting gradient colours. This is not currently implemented so your color state defintion needs to be an array of just 1 colour object
{% endhint %}

## **Configurable properties**

<details>

<summary><strong>bindingPropertyName</strong></summary>

**string** - the parent property name from defaultState with which to connect to.

<mark style="color:red;">**mandatory**</mark>

</details>

<details>

<summary><strong>allowCheckbox</strong></summary>

**bool** - specifies whether you want a checkbox to the left of the colour picker.

The checkbox is bound to _parentProperty.enabled_

defaults to true

</details>

<details>

<summary><strong>hasOpacity</strong></summary>

**bool** - specifies whether you want the opacity input box to appear to the right of the colour picker

defaults to true\


</details>

<details>

<summary><strong>disabled</strong></summary>

**bool** - if set to true this will disable the input box for interaction

defaults to false

</details>
