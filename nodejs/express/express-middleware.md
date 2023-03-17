# Express middleware.

Express middleware is widely used method in express module. Basically almost every method
in the module extends a middleware.

## About.

Middleware is a method on express or basically is amethod that runs before the request reaches
the server for the main function to be run.

## usage.

```js
const express = require("express");
const expressInstance = express();

// middleware function.
const logger = (req, res, next) =>{
    console.log("this is a middleware!");
    return next();
};

expressInstance.get("/", logger function(req, res){
 return res.status(200).json({message:"Ok"});
});

/**
    This is also correct
expressInstance.get("/", [logger,<more middlewares> ] function(req, res){
 return res.status(200).json({message:"Ok"});
});

**/


expressInstance.listen(8000);

```

From the above block of code, one could notice that, the logger function. Which is the
middleware method is refrenced as the second parameter to the **"/"** home route.
<br/>
This means whenever we visit that url, the middleware will always run first before the callback
method run.

## Better usage.

For some reason you might want to apply the middleware on every route, then u nee to use a special method
of the express module known as **app.use()**.

```js
const express = require("express");
const expressInstance = express();

// middleware function
function logger(req, res, next) {
  console.log("i am a middleware!");
}

expressInstace.use(logger); // will be used for every route.

app.get("/", function (req, res) {
  res.status(200).json({ message: "ok" });
});

expressInstance.listen(8000);
```

Now the **logger** method will now be used for all the url routes.

The middle can also be used in this way.

```js
const express = require("express");
const expressInstance = express();

const logger =()=>console.log("hi am a middleware");
const authorization=()=>console.log("hi i am auth");

expressInstance.use([authorization, logger]); // for all routes
expressInstance.use("/", logger); // for a single route.
expressInstance.use(["/auth/users", "purchase/"], authorization); // for specified routes in the list

...

expressInstance.listen(8000);

```
