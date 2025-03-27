# Building your first addon

To help you get started with building an addon using Angular we've created a sample project which you can clone down from GitHub.  This project has all the lifecycle hooks set up and includes the Squirrel Helper Library for you. &#x20;

### Clone the project from GitHub

```
git clone https://github.com/Squirrel-365/Squirrel-Addon-Angular.git
```

### Run the addon

Once cloned cd into the project folder, and then you will need to install all the dependencies and run the project to be able to see it in Squirrel.

```
npm install
npm run start
```

This will run the addon on http://localhost:4401/

### Testing the addon in Squirrel

Open Squirrel and add the "Add-on Developer Program" component to the canvas

![](<../../../.gitbook/assets/image (24).png>)

Once added, enter the addon URL (http://localhost:4401/) in the properties panel and click the "Get json files" button .

{% hint style="danger" %}
_ensure you add a slash at the end of the URL_
{% endhint %}

_This will load up the properties panel, and show the addon web application_

![](<../../../.gitbook/assets/image (25).png>)

## Walkthrough video

{% embed url="https://www.loom.com/share/8bcde15bfc714cf08999b678ec47b9d8" %}
