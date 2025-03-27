# Sending and Receiving Data

## Handshake

When you add an add-on to a Squirrel project, or open a Squirrel project with an add-on in it. Squirrel loads up the add-on in an iframe and a handshake occurs between the add-on and Squirrel.

This same flow happens during design time (in the Squirrel designer application) and at runtime (in the browser)

* The add-on sends a message to Squirrel once it has initialised and is ready to start receiving data and messages.
* Squirrel receives this message and responds with:
  * The current copy of state for the add-on, this includes any bound values or saved properties
  * The size of the component
  * The size of the main canvas and the colour of the main canvas
    * Introduced in 1.12.x
  * The [runtime mode](../../angular/methods/getruntimemode.md) of Squirrel.  This could be design, interactive, preview or live
    * Introduced in 1.12.x
* The conclusion of the handshake triggers the [initState ](../events/oninitstate.md)event in the add-on.

## Receiving data from Squirrel

Once a handshake has concluded between Squirrel and the add-on, Squirrel sends a message every time the value for a property specified in the messageBinding.json and proppertyPanel.json files changes.  This message triggers the [onPropertyChanged ](../events/onpropertychange.md)method on the addon for every property which change.  It also triggers the [onPropertyChangesComplete](../events/onpropertychangescomplete.md) method.

<details>

<summary>onPropertyChange</summary>

Called whenever a property value has changed in Squirrel, state is automatically updated to reflect the new value and this callback is designed to allow you to process that change if needed. The full [dot notation](../../dot-notation.md) name of the property is provided as well as the new, incoming, value.

</details>

<details>

<summary>onPropertyChangesComplete</summary>

Called when all individual [onPropertyChange ](../events/onpropertychange.md)events have been sent. For example if something has happened in Squirrel which causes one or more bindings to be updated these individual bindings are sent as [onPropertyChange ](../events/onpropertychange.md)events. This onPropertyChangesComplete event is executed at the end to advise all changes have been sent to the addon.

This can be very useful if you need to wait for all changes to be received before processing the changes to state.



</details>

## Sending data to Squirrel

If you want to send data back to Squirrel from your addon you can do this by using the [sendToSquirrel](../methods/sendtosquirrel.md) method.  This method takes 2 mandatory and 1 optional parameters

* **property**:  This is the [dotnotation ](../../dot-notation.md)for the property in state you want Squirrel to store the value you are sending.  If this property has been bound to a spreadsheet cell in the property panel then the value sent will be inserted into the spreadsheet.
* **value**:  This is the value ([number, string or array](../../../building-an-addon/communication.md#example-data-structure)) to send to Squirrel
* **padData**:  This defaults to true.  This will check the [binding dimensions](../methods/getbindingdimension.md) for the property and ensure the structure of the data sent to Squirrel matches that size.  This prevents erroneous values from being left in state or the spreadsheet if the size of the value being passed changes.  Leave this as default unless you are explicitly ensuring the dimension of the data passed matches what Squirrel is expecting.
