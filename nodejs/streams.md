# Streams.
You man not always want to read a whole file into a varianble. Cus sometimes, the variable
might not be able to contain a large stream of text of about 1gb. This is where streams comes in.

## About. 
streams is a ways to read a data in smaller chuncks to prevent buffer overflows and too much memory heap.

## Usage.
```js
const {createReadStream} = require("fs");

const readFileStream = createReadStream("./content/test.txt", "utf8");

readFileStream.on("data", (data)=>{
  console.log({data});
})


```

one will notice that the data is being read in chucks.
