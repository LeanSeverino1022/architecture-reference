# pub_sub_with_jquery

This sample uses jQuery, a framework which allows us to publish & subscribe to events really easily, using .on() and .trigger(), which lets us trigger events. 

The app we will be building is very simple, it’s a little app that lets you send messages to yourself.

There are three key parts:

* User sends a message via the form,
* message is shown on the right panel,
* flash notice displays on top of screen to notify user.

All of our code will go inside a JavaScript object I’m going to call pubsub, although in real life it would most likely be called something more relevant to your app:

In practise, each module would probably have its own namespace and have its events in there, such as:

```
pubsub.messages.send
pubsub.messages.receive
pubsub.flash.show
pubsub.flash.hide
```

But as we have only 3 events, I’m going to keep them in the main pubsub namespace. So lets create our event for the sending of a message. Within our pubsub object, add this method:

```
sendMessage: function() {
	var message = $("input").val();
	$("body").trigger("messageReceived", { message: message});
	return false;
}
```

Notice how with .trigger() we can send extra data through as the second parameter, so this makes it easy to send custom data with our custom events.

[If you would like to read the whole post](https://javascriptplayground.com/a-jquery-pub-sub-implementation/)