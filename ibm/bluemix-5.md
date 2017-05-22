The Bluemix platform has a ton of built-in infrastructure components that you can use to add new capabilities to your platform.  When you provisioned your example application, a Cloudant CouchDB server was provisioned to power it. In this challenge, you'll be asked to store the parameters of an incoming request in your database.

### Victory conditions

* Enhance your Node-RED handler function to extract information from query parameters
* Render an HTML response using a template node
* Save the information from the incoming request in your CouchDB/Cloudant database
* Demo your integration for an NPC to score points!

### The path to victory

This time, we'll be enhancing our flow from before in a few key ways.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/save_to_database.original.png"/>

We've added a few new nodes:

* A template node to render HTML in response to an HTTP request
* A Cloudant database node to save data from the incoming request

#### Enhancing the function handler

Rather than just setting a string value, we're going to start collecting some data from the request and creating a `payload` object resembling some real user data in our Function node.

```js
var name = msg.req.query.name || 'New user';
var color = msg.req.query.color || 'blue';
msg.payload = {
    name: name,
    color: color,
    timestamp: new Date()
};

return msg;
```

This function code will look for `name` and `color` query parameters from an incoming request and add them to the payload object, along with a timestamp.

#### Saving data in Cloudant

The database your app is already using can be used to store whatever other data you feel might be helpful. Drag in the Cloudant storage output node and select the database that was already created for your application.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/database_config.original.png"/>

#### Introducing a template

Rather than having the function return content directly, we want to use a template to render data from the payload.  Insert a template node between the Function and Response output nodes with the following HTML template (using Mustache for dynamic content).

```html
<html>
    <body>
        <h1>Hello {{ payload.name }}</h1>
        <p>
            Your favorite color is
            {{ payload.color }}
        </p>
    </body>
</html>
```

Now, when you make a request to `https://<your app>.mybluemix.net/hello?name=Sue&color=purple`, you should get both a nice HTML template back, and have saved the information about your incoming request to Cloudant. You can explore the contents of your database [via the Bluemix console](https://console.ng.bluemix.net/dashboard/services) by drilling into the Cloudant service that was created for you earlier.

Once you've confirmed that you can render HTML and save content in a database, you're all set!  Wave an NPC over to receive your reward.
