
<img src="https://images.unsplash.com/photo-1584949091598-c31daaaa4aa9?crop=entropy&cs=srgb&fm=jpg&ixid=MnwxOTcwMjR8MHwxfHNlYXJjaHwxMHx8ZGV2ZWxvcGVyfGVufDB8fHx8MTY1MjE3Mzk3Ng&ixlib=rb-1.2.1&q=85" height="150">
# Introduction

## Introduction to addons <a href="#inlineextension-introduction-to-addons" id="inlineextension-introduction-to-addons"></a>

The addon framework in Squirrel was first introduced in 1.7 (April 2021) and allows for external developers to create components and functions to be used within Squirrel.

The first release of the framework provided lots of capabilities to the addon author, however the end user experience within the Squirrel designer wasn’t in line with other native components.&#x20;

In build 1.11 (Q1 2022) we have enhanced the addon framework to address these UX concerns.

* Addons now appear in the component and function libraries as individual components rather than a generic “Addon” component
* Authors can provide an icon when submitting their addons, and this icon will be used within the Squirrel designer.
* Authors can now create their own properties panel for their addons.

### Components vs Functions vs Connections

A **component** is something in Squirrel which has a visual element, such as a chart or button or text box. Components can be used to just display data or can be used to capture user interaction.

A **function** is something in Squirrel without a visual element. Functions are usually triggered by something happening in the Squirrel project. They are used to move and/or transform data. An example could be a function which sorts / filters a list of values.

A **connection** is something which connects to an external source and brings back data. For example connecting to a Google spreadsheet and bringing back the data.

&#x20;

With the addon framework you can create your own components and functions. It is not currently possible to create custom connections.

### Integration <a href="#integration" id="integration"></a>

Addons are stand alone web applications which are embedded within a Squirrel project. Squirrel can pass and receive data between itself and the addon. Details on this communication mechanism can be found [here](building-an-addon/communication.md#inlineextension-communication-overview).

For components the addon web application is embedded as an iframe with it’s size and position being determined by the author, or optionally by the [addon itself](building-an-addon/communication.md#resizing-and-repositioning-in-squirrel). For functions the web application is still embedded as an iframe however it’s visibility is hidden. This allows for communication to still occur between Squirrel and the addon however no UI element is rendered.

\


![](<.gitbook/assets/image (5).png>)
