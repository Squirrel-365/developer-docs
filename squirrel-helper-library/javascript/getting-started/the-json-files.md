# The JSON files

As covered in the [Property Panel](../../../building-an-addon/property-panel/) section there are three JSON files which are needed for the add-on to work.  They handle your state definition, communication between the add-on and Squirrel and how to display the property panel in the designer.

<details>

<summary>defaultState.json</summary>

The default state is a JSON representation of the data model you want Squirrel to use when it saves a project with your addon in, and when it adds your addon to the Squirrel canvas for the first time.

This JSON object is available inside your addon via the getter [getCopyOfState()](../../angular/methods/getcopyofstate.md) this returns a copy of the state object.  To set properties of state you need to send the data to Squirrel using the [sendToSquirrel()](../../angular/methods/sendtosquirrel.md) method.  If the property you are updating has been bound to a spreadsheet cell in Squirrel, the data you pass will be inserted into the relevant cell(s).

</details>

<details>

<summary>messageBindings.json</summary>

This file lets Squirrel know whether the property in defaultState in the addon is to be used to:

**send** data from the addon to Squirrel, &#x20;

**receive** data from Squirrel into the addon or

**both** send and receive data

</details>

<details>

<summary>propertyPanel.json</summary>

This file contains a JSON representation of the property panel.  You create the panel using a collection of pre-defined [elements ](../../../building-an-addon/property-panel/property-panel-elements/)available.

</details>
