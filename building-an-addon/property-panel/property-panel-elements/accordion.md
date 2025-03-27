# Accordion



{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (9).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "Accordion",
    "properties": {
        "name": "General",
        "collapsed": false
    },
    "children": []
}
```
{% endtab %}

{% tab title="State definition" %}
As this element is used for grouping other elements within, there is no need to reflect this element in the defaultState.json
{% endtab %}
{% endtabs %}

Can contain other elements as children.

## **Configurable properties**

<details>

<summary>name</summary>

**string** - The text to display as the title of the accordion in property panel.

</details>

<details>

<summary>collapsed</summary>

**bool** - Whether the accordion should be collapsed by default

</details>

<details>

<summary>children</summary>

**array** - An array of other elements to appear inside the accordion drawer

</details>
