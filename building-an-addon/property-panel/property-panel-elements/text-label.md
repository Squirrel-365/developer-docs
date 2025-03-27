# Text Label

{% tabs %}
{% tab title="Property JSON" %}
```json
{
    "type":"Label",
    "properties": {
        "text" : "This is a text label"
    }
}
```
{% endtab %}

{% tab title="State definition" %}
As this element is used for grouping other elements within, there is no need to reflect this element in the defaultState.json
{% endtab %}
{% endtabs %}

{% hint style="info" %}
For build 1.11.x of Squirrel the type needs to be _HTMLLabelElemen&#x74;**.**_\
note: this type has been deprecated in 1.12.x onwards for the above type
{% endhint %}

## Configurable Properties

<details>

<summary>text</summary>

**string** - this is the text to display in the label

</details>
