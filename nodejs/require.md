# Require

## About
The **require** statement in javascript is used to import a module exported from 
one js file to another js file.

**NOTE** You can also import a module without having to export an object from that file.
When this happens, it will invoke any function in that module.


## Usage
In the example below, we will export an object and import it in another using **modules.export** and **require**

```js
//file1.js
module.exports.something = "abc";
```

imported to another file.
```js
//file2.js
const obj =  require("./file1.js");
console.log({obj});
```
