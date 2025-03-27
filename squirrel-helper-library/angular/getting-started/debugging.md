# Debugging

As part of developing you may want to add some debug messages into your code.  These would normally be visible in the browser developer console, however as you are using the Squirrel designer application rather than a browser it's not immediately clear how to view the console.

* With Squirrel running, open a Chrome web browser and navigate to the URL **http://localhost:8315**
* Select your addon from the list
* You will now see the developer tools for your addon, including the console.

### addon framework debug messages

As part of the addon framework we have added a number of debug messages in, to help during development.  These messages are automatically supressed when you build or run your addon in prod mode.

The debug messages are added when you super any of the lifecycle [events ](../events/)from the helper library.

{% embed url="https://www.loom.com/share/f348988263474950861228b799ac9a02" %}
