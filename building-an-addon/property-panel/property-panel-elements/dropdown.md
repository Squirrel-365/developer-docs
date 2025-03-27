# Dropdown

{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (6).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "Dropdown",
    "properties": {
        "labelName": "QR type",
        "options": [
            {
                "option": "",
                "text": "Please Select"
            },
            {
                "option": "url",
                "text": "Website address"
            },
            .......
        ],
        "bindingPropertyName": "qrType"
    }
}
```
{% endtab %}

{% tab title="State definition" %}
The property name needs to match the string specified in bindingPropertyName property. The dropdown matches against default state using the "option" property

```json
{
    "qrType": "url"
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
    "option": "url",
    "text": "Website address"
}
```

**option**  - is the value which will be put in state when the option is selected in the dropdown

**text** - is the text to display in the dropdown

</details>
