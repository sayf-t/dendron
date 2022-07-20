---
id: j8tqt15msi8hn47a3u8ak5h
title: Csv Parse
desc: ''
updated: 1658187377451
created: 1658141747125
---
Ref: /Users/sayf/Documents/ZTM_Node/index.js
https://csv.js.org/parse/
https://nodejs.org/api/fs.html#filehandlecreatereadstreamoptions

## Event Emitter
In node all streams are implemented using the EventEmitter - the events are emitted by Node and we just react to the events on that stream using the `on()` function

## Why use event emitter for our CSV?
The CSV had a LOT of planets - need to support large datasets and be able to work with them in a performant efficient way
- Need to read in the data line-by-line from the start of the file
- Doing this allows us to handle the data as it comes in, rather than waiting for all the data to be read, so no one is waiting around needlessly
- So we will use the stream API in combination with some of Node's built-in streaming capability (seen in HTTP servers)
- So, it's good to stream large datasets!

## fs.createReadStream(path[, options])
https://nodejs.org/api/fs.html#class-fsreadstream
- Readable stream is a kind of event emitter that emits various different named events depending on what is happening to the file
- when running `node index.js` we get Node arrays of buffers which are representations of collection of bytes 
- the read stream is reading raw bits and bytes - we still need to parse the results!

## How do we connect the parse functions with the createReadStream for our file?
- The parse function with the `pipe()` function!
- It is used to connect a readable stream source with a destination


