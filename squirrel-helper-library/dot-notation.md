# Dot notation

When dealing with binding information to and from Squirrel, or referencing a particular property in state, the Squirrel helper library leverages dot notation. For example:

{% tabs %}
{% tab title="JSON Model" %}
```json
{
  "buttonText": "Load File",
  "buttonDisabled": "false",
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
  },
  "dataDestination": ""
}
```
{% endtab %}

{% tab title="Examples" %}
Some examples of dot notation for this state

* buttonText
* buttonColor.type
* buttonColor.color.0.alpha
  * For arrays of properties the index in the array is provided as a number as part of the dot notation.
{% endtab %}
{% endtabs %}
