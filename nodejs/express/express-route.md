# Express route.

There is a better way to route in an express application. Instead of just using **app.get()** and
other related methods, the is a better way of doing this.

## About.

The **express.Router()** instance of the express module helps to organize routes in a more
consice and prefered way. We can combine theme in a way that is more suitable and human comprehendable

## Usage.

```js
// middlewares.js
const express = require("express");
module.exports = [
  express.json(), // posted json requests.
  expres.urlencoded({ extended: false }), // encoding formdata post request.
  express.static("./public"),
];
```

<br/>

```js
// file1.js
const express = require("express");
const expressRoute = express.Router();

expressRoute.get("/", function (req, res) {
  return res.status(200).json({ message: "hello world" });
});

expressRoute.post("/", function (req, res) {
  return res.status(200).json({ message: "ok" });
});

module.exports = { PeopleRoute: expressRoute };
```

<br/>

```js
//file2.js
const express = require("express");
const expressInstance = express();
const { PeopleRoute } = require("./file1.js");
const Middlewares = require("middlewares.js");

expressInstance.use(Middlewares);

expressInstance.use("/people", PeopleRoute); // all people routes.

expressInstance.listen(8000);
```

<br/>
Even better we can chain the routes
```js
//file2.js

//...
expressRoute.route("/").get(function(req, res){}).post(function(req, res){});

//...
```
