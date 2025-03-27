# Checkbox

{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (19).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "Checkbox",
    "properties": {
        "labelName": "Auto Play",
        "bindingPropertyName": "autoPlay"
    }
}
```
{% endtab %}

{% tab title="State definition" %}
The property name needs to match the string specified in bindingPropertyName property. The boolean value will be the default state of the checkbox

```json
{
    "autoPlay": true
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
