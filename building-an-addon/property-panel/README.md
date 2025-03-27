# Property Panel

To build a property panel for your addon to appear in Squirrel you need to create three files:

1. defaultState.json
2. messageBindings.json
3. propertyPanel.json

With these three files Squirrel knows how to load your addon, how to communicate with your addon, and also how to draw your property panel.

## defaultState.json

The default state is a JSON representation of the data model you want Squirrel to use when it saves a project with your addon in, and when it adds your addon to the Squirrel canvas for the first time.

When adding a new addon to the canvas, Squirrel will use this default state to set up your default values, which are used by the property panel. When changes are made, either direct from the property panel, or if a binding changes, then the updated values are stored in the state within Squirrel. This addon state is saved into the Squirrel file when a project is saved.

Here is an example of default state for a simple addon:

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

* Button text is a simple string, with the default being “Load File”
* For buttonColor we want to use a colour picker in the properties panel to allow the end user to select the colour. As such this property has to follow the default state structure for the colour object. Details on all the property controls and their default state structures can be found [here](property-panel-elements/).
* Data destination is only going to be used to have data passed to it from your addon. This property isn’t going to appear in the property panel, so we can initialise it as an empty string.

## messageBinding.json <a href="#messagebinding.json" id="messagebinding.json"></a>

As you’ve seen with the default state, some of the properties will be used by the property panel to set up or style your addon, e.g. the buttonText and buttonColour properties. Where as some properties will only be used as a placeholder in Squirrel to receive data from your addon, e.g. the dataDestination property. And sometimes you may want a property to do both, send data to the addon, and also receive data back from the addon.

Telling Squirrel which properties require which type of communication is handled via the messageBinding.json file.

Here is an example:

```json
[
    {
        "property": "buttonText",
        "direction": "receive"
    },
    {
        "property": "buttonColor",
        "direction": "receive"
    },
    {
        "property": "dataDestination",
        "direction": "send"
    }
]
```

This file is an array of objects which detail the name of the property and which direction communication should flow. The direction is written from the point of view of the addon, so “receive” is that you want the addon to be able to receive this data, but will not send it to Squirrel

* **Property** is the name of the property you want to set up the communication for. In the case of buttonColor, which has sub properties defined in the default state. You only need to set the message binding direction on the parent property and all children will inherit from that
* **Direction** specifies which way you want data to flow.
  * **receive** means you want the addon to receive changes to that property whenever it’s value in state changes
  * **send** means you want the addon to be able to send updates to that properties value to Squirrel. Squirrel will then process those changes and store them in state, and if there is a binding attached to that property, the values you pass will be loaded into the relevant cells in the spreadsheet
  * **both** means you want the addon to be able to both receive data from Squirrel and also send data back to Squirrel for the same property.
    * With both communication direction set, you need to ensure you validate incoming / outgoing data to prevent becoming stuck in a perpetual loop. Sending an update to a value, which triggers Squirrel to send it back, which triggers the addon to send it back to Squirrel etc.
    * Squirrel and the helper library attempts to prevent this cyclical loop from occurring, but it is strongly suggest that as the addon author you also validate data to ensure only changes to values are sent to Squirrel.

## propertyPanel.json <a href="#propertypanel.json" id="propertypanel.json"></a>

Once you’ve set up the default state, and you’ve configured the binding directions the last piece we need to define is the actual property panel itself. This again is a JSON object that lists which property elements you want, in what order, and what property in default state you want the interaction to relate to.

Here is an example of a simple property panel

```json
[
    {
        "type": "Accordion",
        "properties": {
            "name": "General",
            "collapsed": false
        },
        "children": [
            {
                "type": "InputBox",
                "properties": {
                    "labelName": "Button Text:",
                    "allowBinding": true,
                    "allowManualEntry": true,
                    "textArea": false,
                    "bindingPropertyName": "buttonText"
                }
            },
            {
                "type": "InputBox",
                "properties": {
                    "labelName": "Data Desination:",
                    "allowBinding": true,
                    "allowManualEntry": false,
                    "bindingPropertyName": "dataDestination"
                }
            },
            {
                "type": "ColorOpacityInput",
                "properties": {
                    "labelName": "Button Color",
                    "bindingPropertyName": "buttonColor",
                    "allowCheckbox": false,
                    "hasOpacity": false
                }
            }
        ]
    }
]
```

We provide a collection of elements you can use in the property panel. Each element requires a different set of properties, and has their own defined state which you need to include in the [default state ](./#defaultstate.json)definition.&#x20;

Details on the elements available, the properties they have and the corresponding data state structure can be found next.

\
