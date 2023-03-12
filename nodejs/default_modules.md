# Default modules

**Table of content**

1. [About](#about)
1. [Modules](#modules)
1. [os module](#os-module)
1. [path module](#path-module)
1. [fs module](#fs-module)

---

## About.

Node environment provides some default modules to use for handling different and common js
requirements. These modules can be imported and use any for usege.

## Modules.

Below are some of the modules to be used for most basic requirementing when building in nodejs.

- os module
- path module
- fs module

### os module.

The **os** module has many properties and objects for working with os related matters.

#### usage.

```js
// os - object containing properties of the operating system.
// path - allows to manupulate filepath and dirpath.

//os-module

const os = require("os");
console.log({
  uptime: os.userInfo(),
  name: os.type(),
  release: os.release(),
  totalMem: os.totalmem(),
  freeMem: os.freemem(),
});

// many more properties.
```

---

### path module.

The **path** module helps with all relative and absolute path matters in node js.

#### usage.

```js
// path-module
const path = require("path");
console.log({
  osSeparator: path.sep, // log sperator for this os path routing // log sperator for this os path routing.
  joinPath: path.join("/content", "subfolder", "test.txt"), // "/content/subfolder/test.txt"
  baseName: path.basename(path.join("/content", "subfolder", "test.txt")), // test.txt
  absolutePath: path.resolve(__dirname, "content", "subfolder", "test.txt"), // /home/escobar619/Documents/Dev/.../content/subfolder/test.txt
});
```

---

### fs module.

The fs module is related to managing most file related manipulations like creating a file, updating a file, removing a file, reading the content of a file. .

#### usage.

below is a txt file with path _./content/first.txt_

```txt
hello world this is file one
```

and anotherfile with path _./content/second.txt_

```txt
what a wonderful world.
```

```js
const { readFileSync, writeFileSync } = require("fs");
const first = readFileSync("./content/first.txt", "utf8");
const second = readFileSync("./content/second.txt", "utf8");
console.log({ first, second });

writeFileSync(
  //write to a file when it's exist or create a new one.
  "./content/result-sync.txt",
  "writing content of both files: " + first + ", " + second,
  { flag: "a" } // to append to the file
);
```

In the above code example, we used the **readFileSync** & **writeFileSync** which reads data from a file _synchronously_. This method
can be ignored for a better version of reading and writing file _asynchronously_.
We can use a method from **fs** module known as **readFile** & **writeFile**, these methods reads and writes
to a file asynchronously.

it can be use like so.

```js
const { readFile, writeFile } = require("fs");

readFile("./content/first.txt", "utf8", readFileHandler);

writeFile(
  "./content/result-async.txt",
  "content to be written",
  writeFileHandler
);

function readFileHandler(err, result) {
  if (err) return console.log("Filed to read file! ", err);

  //logic functionality
  console.log({ result });
}
function writeFilehandler(err, result) {
  if (err) return console.log("Filed to write to file! ", err);

  //login functionality
  console.log({ result });
}
```
