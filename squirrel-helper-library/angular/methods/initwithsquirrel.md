---
description: initWithSquirrel();
---

# initWithSquirrel

## initWithSquirrel()

No parameters and no return.

This method should be called once the addon has finished it’s own configuration and initialization. This will send a message to Squirrel to inform it that the addon is setup and ready to start sending and receiving messages.

This method will store a copy of state and bindingDimensions.

### state

{% tabs %}
{% tab title="Description" %}
Squirrel will respond to the [initWithSquirrel()](initwithsquirrel.md#initwithsquirrel) method call with a handshake response. The handshake will include a complete copy of state.

State matches the [defaultState ](../../../building-an-addon/property-panel/#defaultstate.json)structure provided in the [defaultState.json](../../../building-an-addon/property-panel/#defaultstate.json) file. The state object passed from Squirrel will contain all the current values for any bound cells or hard-coded values in the property panel.

State is a private variable which you cannot access directly, however you can request a copy of state by using the [getCopyOfState()](getcopyofstate.md) method. And a copy of state is passed into the [onInitState(state: any)](../events/oninitstate.md) method.
{% endtab %}

{% tab title="JSON" %}
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
{% endtabs %}

### bindingDimensions

{% tabs %}
{% tab title="Description" %}
Squirrel will respond to the [initWithSquirrel()](initwithsquirrel.md#initwithsquirrel) method call with a handshake response. The handshake will include a complete copy of all the known bindings.

The bindingDimensions object will contain a property name matching your default state, following [dot notation](../../dot-notation.md), with the value being the size of the binding.

This variable is private and not directly accessibly, however you can get the dimension for a specific property by calling the [getBindingDimension(property: string)](getbindingdimension.md) method

\

{% endtab %}

{% tab title="JSON" %}
```json
{
  "buttonColor.color.0.color":{
    "width":1,
    "height":1
  },
  "buttonText":{
    "width":1,
    "height":1
  }
}
```


{% endtab %}
{% endtabs %}
