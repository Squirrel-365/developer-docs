# Sub Accordion

{% tabs %}
{% tab title="Image" %}
![](<../../../.gitbook/assets/image (20).png>)
{% endtab %}

{% tab title="Property JSON" %}
```json
{
    "type": "SubAccordion",
    "properties": {
        "name": "tooltips",
        "collapsed": true,
        "checkBox": false,
        "bindingPropertyName": "tooltipEnabled"
    },
    "children": []
}
```
{% endtab %}

{% tab title="State definition" %}
If you set the check box property to true, then you will need ensure a binding property name is specified and matches a property in default state

```json
{
    "tooltipEnabled": false
}
```
{% endtab %}
{% endtabs %}

Can contain other elements as children.

## **Configurable properties**

<details>

<summary>name</summary>

**string** - The text to display as the title of the sub accordion in property panel.

</details>

<details>

<summary>collapsed</summary>

**bool** - Whether the sub accordion should be collapsed by default

</details>

<details>

<summary>checkBox</summary>

**bool** - Whether to show a check box to the right of the sub accordion.  An example of this check box could be to toggle on or off collection or properties.  E.g. on a chart the tooltips sub accordion has a check box,  if unchecked tooltips are not applied.&#x20;

</details>

<details>

<summary>bindingPropertyName</summary>

**string** - the property name in default state with which to connect the checkbox to. &#x20;

_Note: This is mandatory if checkBox is set to true._

</details>

<details>

<summary>children</summary>

**array** - An array of other elements to appear inside the sub accordion drawer

</details>
