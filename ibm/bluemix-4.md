## Path to Victory

To successfully complete this challenge you will need to use three nodes from the palette.

<img src="https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/request.original.png"/>

* The HTTP request input node
* The Function node
* The HTTP response output node

The request node will accept an incoming request on a route you specify, such as `https://<my-app>.mybluemix.net/hello`. Next, you will write a [function](http://nodered.org/docs/writing-functions) which adds a string `Hello, world!` to the `msg.payload` property.

```js
node.log('About to handle a request...');
msg.payload = 'Hello, world!';
return msg;
```

Finally, you will pass the message to an HTTP response output node. From your function, you can set `msg.body` to set the actual content of the response.

For this challenge, all you need to do is send a string "Hello, World!" in response to an HTTP request to your application.