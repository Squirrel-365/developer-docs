# Communication

## Communication overview <a href="#inlineextension-communication-overview" id="inlineextension-communication-overview"></a>

Squirrel embeds an addon in an iframe and communicates back and forth with it via JavaScript [post messaging](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage). As Squirrel could have multiple addons in the same project Squirrel needs a way to identify which addon to send data to, and which addon has sent data back. This is handled in the Squirrel helper library for you, but for background here is a summary of what it’s doing:

1. When Squirrel embeds an instance of your addon in a project it generates a unique ID for that instance.
2. This ID is added to the URL string for your addon as a query parameter
3. The addon framework gets this ID and this is included in all messages to Squirrel.
4. Squirrel uses this unique ID when sending messages to ensure the message gets sent to the correct addon.

### Handshaking

Before Squirrel can send data to an addon it needs to know when the addon is ready to receive data. This is achieved via a handshake.

Once you have done any setup and initialization on your addon and you’re ready to process messages from Squirrel. You need to call the [initWithSquirrel ](../squirrel-helper-library/angular/methods/initwithsquirrel.md#initwithsquirrel)method, from the Squirrel helper library. This sends a message to Squirrel to advise it the addon is ready and waiting. Squirrel then responds with the [initState ](../squirrel-helper-library/angular/events/oninitstate.md)message, which the Squirrel helper library validates and then calls a number of corresponding callback methods in your addon. By overriding these callback methods you can then process the data being sent.



### Binding Dimensions

When binding a property to cell(s) in Squirrel it is useful to know the size of the range of cells selected. For example

* Has a property only been bound to a single cell e.g. 1 column by 1 row.
* Has it been bound to a range of cells. e.g. 2 columns by 3 rows etc

Knowing the dimensions of the binding means that you can ensure the data you send to Squirrel matches the correct structure.

* For **single cells**
  * Squirrel expects a primitive values (eg string, bool, number etc)
* For **multiple cells**
  * Squirrel expects a multi dimensional array for the row and columns.
    * Rows are made up of arrays of primitive values. Each value represents the column
    * The data is then made up of an array of rows.

### Example data structure

<details>

<summary>single cell</summary>

```json
"Hello"
```

</details>

<details>

<summary>3 rows of 2 columns</summary>

```json
[
 ['cell A1', 'cell B1'],
 ['cell A2', 'cell B2'],
 ['cell A3', 'cell B3'],
]
```

</details>

<details>

<summary>1 row of 2 columns</summary>

```json
[
 ['cell A1', 'cell B1']
]
```

</details>

### Sending Data to Squirrel <a href="#sending-data-to-squirrel" id="sending-data-to-squirrel"></a>

Once your addon is setup and has processed the incoming state from Squirrel, you may need to send information back for Squirrel to insert the data into cells in the spreadsheet. This is handled by calling the [sendToSquirrel ](../squirrel-helper-library/angular/methods/sendtosquirrel.md)method in the Squirrel helper library.

Passing the variable name (matching a variable in [default state](property-panel/#defaultstate.json)) and the data to send to Squirrel. This method constructs the message body and sends the data off to Squirrel. An optional parameter to include at the end of the method call is a bool to advise whether to pad the data. This is set to true by default.

Padding the data is where the helper library will check the binding dimensions of the property you are sending, and ensure the data you’re passing is the correct size. This is accomplished by either adding extra rows or columns in to the array with nulls. Passing a padded data structure means that Squirrel will always overwrite all cells in the binding range ensure there are no erroneous values left over from a previous message.

### Blocking interactions in Squirrel

Addons in Squirrel block mouse events from passing through to underlying components.  So for example a button behind your addon will not be clickable.   It is possible to globally tell Squirrel that your addon does not require interaction (thereby allowing all events to pass through).  This is done when you [publish the addon](publishing-an-addon/)

{% hint style="info" %}
The no interaction setting will prevent any events from triggering in your addon.
{% endhint %}

### Resizing and repositioning in Squirrel

Sometimes you may want to resize or change the location of your addon component in Squirrel. For example if your addon needs to expand or shrink to show / hide additional content.  This can be achieved by calling setter methods:

1. [setSize()](../squirrel-helper-library/angular/methods/setsize.md)
2. [setPosition()](../squirrel-helper-library/angular/methods/setposition.md)

Calling either of these methods will update the size / position on the Squirrel canvas, and will trigger an [onPropertyChange ](../squirrel-helper-library/angular/events/onpropertychange.md)event.
