# Font

{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (2).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "Font",
    "properties": {
        "titleLabel": "Title font:",
        "hasAlignment": false,
        "hasCapitalisation": true,
        "hasTitle": false,
        "hasBold": true,
        "hasItalics": true,
        "hasUnderline": true,
        "hasColor": true,
        "hasOpacity": true,
        "hasSize": true,
        "bindingPropertyName": "labels"
    }
}        
```
{% endtab %}

{% tab title="State definition" %}
The property name needs to match the string specified in bindingPropertyName property.&#x20;

```json
{
    "labels": {
        "text": "",
        "enabled": true,
        "font": {
            "weight": "normal",
            "style": "normal",
            "decoration": "none",
            "color": [
                {
                    "color": "#333333",
                    "alpha": 1,
                    "ratio": 0
                }
            ],
            "size": 15,
            "family": "Open Sans",
            "align": "left",
            "verticalAlign": "top"
        },
        "capitalisation": "upper"
    }
}
```
{% endtab %}
{% endtabs %}

This element has a number of configurable properties. If a property has a default value then you do not need to provide it in the propertyPanel.json file unless you want to specify a value different to the default.

## **Configurable properties**

<details>

<summary><strong>bindingPropertyName</strong></summary>

**string** - the parent property name from defaultState with which to connect to.

<mark style="color:red;">**mandatory**</mark>

</details>

<details>

<summary>titleLabel</summary>

**string** - The text to display above the font element as a title

</details>

<details>

<summary>hasAlignment</summary>

**bool** - specifies whether you want to show the alignment buttons or not

defaults to true

![](<../../../.gitbook/assets/image (4).png>)

</details>

<details>

<summary>hasCapitalisation</summary>

**bool** - specifies whether you want to show the capitalisation buttons or not

defaults to true

![](<../../../.gitbook/assets/image (26).png>)

</details>

<details>

<summary>hasTitle</summary>

**bool** - specifies whether you want to show the title or not

defaults to true

</details>

<details>

<summary>hasBold</summary>

**bool** - specifies whether you want to show the bold button or not

defaults to true

</details>

<details>

<summary>hasItalics</summary>

**bool** - specifies whether you want to show the italics button or not

defaults to true

</details>

<details>

<summary>hasUnderline</summary>

**bool** - specifies whether you want to show the underline button or not

defaults to true

</details>

<details>

<summary>hasColor</summary>

**bool** - specifies whether you want the font colour picker or not

defaults to true

</details>

<details>

<summary>hasOpacity</summary>

**bool** - specifies whether you want to show the colour opacity input or not

defaults to true

</details>

<details>

<summary>hasSize</summary>

**bool** - specifies whether you want to show the font size picker or not

defaults to true

</details>
