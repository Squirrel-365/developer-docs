# Radio Button

{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (27).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "Radio",
    "properties": {
        "labelName": "Exported file format:",
        "options": [
            {
                "option": "pptx",
                "text": "PowerPoint"
            },
            {
                "option": "pdf",
                "text": "PDF"
            },
            .......
        ],
        "bindingPropertyName": "fileType"
    }
}
```
{% endtab %}

{% tab title="State definition" %}
The property name needs to match the string specified in bindingPropertyName property. The dropdown matches against default state using the "option" property

```json
{
    "fileType": "pptx"
}
```
{% endtab %}
{% endtabs %}



## **Configurable properties**

<details>

<summary><strong>bindingPropertyName</strong></summary>

**string** - the property name from defaultState with which to connect to.

<mark style="color:red;">**mandatory**</mark>

</details>

<details>

<summary>labelName</summary>

**string** - the text to display above the dropdown as a title

</details>

<details>

<summary>options</summary>

**array** - An array of objects containing an option and text property

```json
{
    "option": "pptx",
    "text": "PowerPoint"
}
```

**option**  - is the value which will be put in state when the radio button is selected

**text** - is the text to display on the radio buttons

</details>
