# Modules in javascript


## About 
modules in javascript are used for scoping variables and other datatypes
in javascript. The modules are what allows for passing javascript objects
around from one code base to another. The file can be imported using the
**require** statement which is part of the **globals** in nodejs.


## Usage
```js
// account.js
const secret = "one";
const name = "two";

module.exports = {secret name};

```

Import the data in another file.

```js
// context.js
const accountInfo = require("./account.js");
console.log({accountInfo});
```

The above will log out all the objects in the exported from the first file.
