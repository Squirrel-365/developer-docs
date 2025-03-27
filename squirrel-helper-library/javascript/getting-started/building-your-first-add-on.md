# Building your first add-on

To help you get started with building an add-on using JavaScript we've created a sample project which you can clone down from GitHub.  This project has all the lifecycle hooks set up and includes the Squirrel Helper Library for you. &#x20;

### Clone the project from GitHub

```
git clone https://github.com/Squirrel-365/Squirrel-Addon-JS.git
```

### Run the add-on

{% hint style="info" %}
To be able to view the add-on in Squirrel you need to be running the add-on in a web server.  If you do not have a web server on your machine there are a number of options:

* [WAMP ](https://en.wikipedia.org/wiki/WampServer)or [LAMP](https://en.wikipedia.org/wiki/LAMP_\(software_bundle\))
* [http-server](https://www.npmjs.com/package/http-server) for node

For this guide we will be using http-server.
{% endhint %}

Once cloned, cd into the project folder and run

```
http-server -c-1 -p 8080
```

This will run the addon on http://localhost:8080/ and disable any page caching.&#x20;

### Testing the addon in Squirrel

Open Squirrel and add the "Add-on Developer Program" component to the canvas

![](<../../../.gitbook/assets/image (24).png>)

Once added, enter the addon URL (http://localhost:8080/) in the properties panel and click the "Get json files" button .

{% hint style="danger" %}
_ensure you add a slash at the end of the URL_
{% endhint %}

_This will load up the properties panel, and show the addon web application_

![](<../../../.gitbook/assets/image (25).png>)
