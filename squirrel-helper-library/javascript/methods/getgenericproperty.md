---
description: getGenericProperty(property)
---

# getGenericProperty

This method converts a [dot notation](../../dot-notation.md) property string into a generic property string.  This will replace the series item numbers in the property string with asterisks. &#x20;

E.g.   series.1.data   would be converted to series.\*.data

This generic property is useful in conjunction with the [onPropertyChange ](../events/onpropertychange.md)event, allowing you to process a change of a series data regardless of which item in the series was updated.

The method accepts the following argument

<details>

<summary>property: string</summary>

A property specified in [dot notation](../../dot-notation.md) for which to convert to a generic property string

</details>
