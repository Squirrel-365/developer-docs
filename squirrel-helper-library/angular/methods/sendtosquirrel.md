---
description: 'sendToSquirrel(property: string, value: any, padData = true): void'
---

# sendToSquirrel

Send data to Squirrel to load into the spreadsheet.  The method accepts the following arguments&#x20;

<details>

<summary>property: string</summary>

The property in [dot notation](../../dot-notation.md) for which the data relates to.&#x20;

</details>

<details>

<summary>value: any</summary>

The data to send to Squirrel.  This could be a single cell, or an array of rows and columns as discussed [here](../../../building-an-addon/communication.md#example-data-structure)

</details>

<details>

<summary>padData: boolean (optional - defaults to true)</summary>

This will check the [binding dimensions](getbindingdimension.md) for the property specified and ensure the structure of the data sent to Squirrel matches that size.  This prevents erroneous values from being left in state or the spreadsheet if the size of the value being passed changes.&#x20;

_Leave this as default unless you are explicitly ensuring the dimension of the data passed matches what Squirrel is expecting._

</details>
