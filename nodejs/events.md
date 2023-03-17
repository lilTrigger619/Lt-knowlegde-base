# Events

## About.
In javascript, one of the well most used module is the event module.
This module is used to listen to an event and handle it with a functional logic
when the event is emmited. 

### usage.

```js
const event = require("events");
const EventEmmiter = new event();

EventEmmiter.on("scream", screamHandler);

const screamHandler = ()=>console.log("Aaah!");

EventEmmiter.emit("scream");
```

In the above code, when the EventListener is created with the on,
the it is listened to with the **emit** method

**NOTE :** Logic must be made from top to down. I.e the listening should be from the top
and the emiting follows.
