## Path to Victory

To complete this challenge, you'll need to add two new nodes to the flow.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/new_nodes.original.png"/>

* One node will send an SMS to a phone number you configure
* One node will limit the number of SMS you send to one message per minute

### Using the "delay" node

In the palette under the "function" heading, you'll find the "delay" node. This allows you to do a variety of things, but in this case you'll need to use it to prevent sending SMS messages out more than once a second. Your configuration will look something like this.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/delay_config.original.png"/>

I chose to drop messages we don't handle, rather than have them queue up.

### Using the Twilio node

To send an SMS, you'll need to drag in and configure a "Twilio" node from the palette. There are two primary pieces of configuration you'll need.  The first is for the number you'd like to send the message to, which is the first screen you'll see if you double click on the Twilio node.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/twilio_out_config.original.png"/>

From within this configuration window, you'll need to set your Twilio account information, such as your auth token and account SID, and the Twilio number you'd like to send messages from.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/twilio_account.original.png"/>

### Wiring them both together

Using the Node-RED editor, you should be able to pass output from the template through the delay node, to the Twilio node, to ultimately send the SMS message.  Once you've managed to send an SMS when the temperature gets too high, wave over an NPC to collect your reward!