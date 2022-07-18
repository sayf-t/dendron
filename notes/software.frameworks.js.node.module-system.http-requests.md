---
id: f725eukmz7sv418jfd5zpnx
title: HTTP Requests
desc: ''
updated: 1658128110098
created: 1658126705066
---

- The require function has set the `http` constant to the set of functions and data that are returned from the `http` module.

`http-example.js`
```js

//const http = require('http');
const { get } = require('http');

// one of the module functions
// const req = http.request('http://www.google.com', (res) => {
const req = get('http://www.google.com', (res) => {
  // eventEmitter in action!
  res.on('data', (chunk) => {
    // data event has a parameter for a chunk of data returned by that event
    console.log(`Data chunk: ${chunk}`);
  });
  //another emitter
  res.on('end', () => {
    console.log('No more data');
  });
});

// req.end(); not needed for get(), needed for request()

```

- using `https` keeps data secure, but if used above, there will be an `ERR_INVALID_PROTOCOL`, as the module being used is `http`;
- so need to use the `https` module when communicating securely
