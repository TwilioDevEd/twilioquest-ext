In the previous mission, you deployed a sample [Node-RED](https://nodered.org/) application to Bluemix. Now, we're going to learn the basics of customizing it and deploying updates to the application.

In this mission, you'll be asked to do two things - configure a simulated IoT sensor into the application flow, and practice dragging, dropping, and configuring nodes in the Node-RED development environment.

### Victory conditions

* Configure a [simulated IoT sensor](http://ibm.biz/iotsensor) to use in development and log output to the debug tab in Node-RED
* Drag and configure a new node into the flow from the palette in Node-RED

### The path to victory

When you deployed the Node-RED boilerplate application, you already had two flows configured. The bottom one was for a fictional "temperature sensor" from an IoT device. You can view the flow editor by visiting `https://<bluemix-app-name>.mybluemix.net/red`.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/bluemix5.original.png" style="width:100%"/>

Node-RED applications are composed from input and output nodes from a palette on the left-hand side of the UI. One of the nodes included by default is a simulated device sensor - it's labeled "IBM IoT App In" in the flow editor.  Double-click on this node to bring up an editor UI.

One of the fields you can edit is the Device ID:

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/bluemix3.original.png" style="width:100%"/>

With the Watson IoT platform you can connect real devices to flows like this in Node-RED, but to get started quickly you can use a simulated device from [http://ibm.biz/iotsensor](http://ibm.biz/iotsensor). Keep this browser window open so you can tweak your sensor's data values that get sent to your Node-RED app. 

Now, we need to configure your Node-RED app with the simulated IoT device's ID - see the randomly generated ID at the top?

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/bluemix4.original.png" style="width:100%"/>

Configure your node with this ID in the Node-RED editor and click the "Deploy" button. Your flow will be redeployed, and you should start seeing output from your simulated device in the "debug" tab of your UI.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/debug-tab.original.png" style="width:100%"/>

If you change the temperature value in the device simulator browser window, you'll see different output start getting logged in your console.  If you dig into what's happening in your flow, you have a "switch" node that prints different output messages based on the current temperature value.

To fully complete this challenge and demonstrate a bit of Node-RED mastery, configure a third template to print a message if and only if the temperature value is equal to `42` (or your own favorite number).  It should ulitimately look something like this.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/Node-RED__twilioquest-test.mybluemix.net_2017-0.original.png" style="width:100%"/>

You'll need to edit the existing switch node, and add another template node from the palette.  When you've got both the simulated sensor and the new node working, call an NPC over to validate your work and get your loot!