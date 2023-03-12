# Express

---

When building a server with nodejs, using the same old http module is quite faustrating.
It's ok if you know your way around javascript very well. But sometimes you would want to just
spind up a server real quick and do some work. That's where **express** module comes in.

## About.

The express module is used to create a server for backend operations and serve server side
rendered apps and also create a restful api.
**Quick example :**

```js
const express = require("express");
const app = express();

app.get("/", function (req, res) {
  res.write("this is the homepage!");
  res.status(200).send();
});

app.get("/about", function (req, res) {
  res.write("this is the about page.");
  res.status(200).send();
});

app.all("*", function (req, res) {
  res.write("Not found!");
  res.status(404).send();
});

app.listen(500, () => {
  console.log("server is listening on port 5000...");
});
```

## Serving static apps.

When you use expressjs to server up some html content like so,
consider the following directories.
_/app/_
_/app/app.js_
_/app/index.html_
_/app/static/style.css_

```js
// file: app.js
const express = require("express");
const path = require("path");
const application = express();

// setup static files.
application.use(express.static("./static"));

// homepage route.
app.get("/", function (req, res) {
  res.sendFile(path.resolve(__dirname, "./index.html"));
});

application.listen(8000, function () {
  console.log("Serving express server on http://localhost:8000...");
});
```

---

In the above code, one could see how simple it is to setup static files
in the express server by using the **express.static()** method.
<br/>
But we can server up the htlm size just as a static file to be rendered.
We can do this by just putting it in the static folder.
<br/>
consider the new directory structure.
_/app/static/index.html_
_/app/static/style.css_
_/app/app.js_

```js
const express = require(" express ");
const serverInstance = express();

// setup static files.
serverInstance.use(express.static("./static"));

serverInstance.listen(8000, function (req, res) {
  console.log("Server listening on http://localhost:8000");
});
```
