---
id: zu7pktdv9xw8blhdrw3j87b
title: Module System
desc: ''
updated: 1658132563465
created: 1658126558597
---

## Why use modules?
Imagine each module is a box. We can combine different modules that work together to achieve our goal
Some reasons:
  - Re-use existing code - don't reinvent the wheel! save time!
  - Organise your code!
  - Expose only what will be used

## Create CommonJS modules
- we can write our own, and organise our own code!
eg
- create new file called `https.js` // for encrypted connection
- create new file called `response.js`
- create new file called `request.js`
- `exports` is used sometimes in place of `module.exports`
- the module object lives in global
  - it includes the `exports` object - needed to include all functions and variables to be available in other modules
  - in Node repl, explore the `require.extensions` object - it tells node to look for `.js` and other files with these extensions in the require statements
  - use it for `module.exports = { send: send}`

`https.js`
```js

const request = require('./request.js');
const request = require('./response.js');

function makeRequest(url, data) {
  request.send(url, data);
  return response.read();
}

const responseData = makeRequest('https://google.com', 'hello');
console.log(responseData);

```
--- 

`request.js`
```js

const REQUEST_TIMEOUT = 500;

function encrypt(data) {
  return 'encrypted data';
}

function send(url, data) {
  const encryptedData = encrypt(data);
  console.log(`sending ${encryptedData} to ${url}`);
}

module.exports = { 
  REQUEST_TIMEOUT,
  send,
}

```

---

`response.js`
```js

// NOTE
// This is not a real read function
// We are not actually decrypting real data
// Might use a library using TLS - a protocol our browsers and servers use when sending encrypted data over the web
// With our functions, we can create skeleton of our request data in https.js

function decrypt(data) {
  return 'decrypted data';
}

function read() {
  return decrypt('data');
}

module.exports = {
  read,
}
```

## CommonJS vs ECMAScript modules
- when using `require()`, it is CommonJS

## Create ECMAScript modules
- in ES6 modules, import/export keyword and statements are used:
`import { send } from './request';`
`import { read } from './response';`
`export {send}`
- sometimes need to set `"type": "module"` in the package.json or use the `.mjs` extension
- node maintains a cache of required modules to see if already-requested modules are in memory
- this cache object is global and lives in `require.cache`

## Using index.js
say we placed our files `request.js` and `response.js` modules in a folder called `internals` - can we `require('./internals')`?
- Yes, with `index.js`, you can treat a folder like a module
- `index.js` tells us what is being exported from a folder
- It exports via:
index.js
```js

module.exports = {
  request: require('./request'),
  response: require('./response'),
}

```

...or if you want to be fancy...

```js
const request = require('./request'); 
const response = require('./response'); 

module.exports = {
  REQUEST_TIMEOUT: request.REQUEST_TIMEOUT,
  send: request.send,
  read: response.read,
};

```
- thus in `https.js`, you could `const internals = require('./internals');`,
or
```js
const { send, read } = require('./internals');
```
- then you could make requests to specific modules via `internals.request.send()` and `internals.response.read()`
- thus index.js allows you to export many modules with reference to paths of folders

### Spread operator
Take all properties in 2 modules and unpack them into new object

```js

module.exports = {
  ...require('./request'),
  ...require('./response'),
}
```

### Should you use index.js?
- some use it as it simplifies using multiple modules
- others prefer to use direct path to modules
- it is good to understand, but it might add some unexpected confusion


### More links

https://nodejs.org/api/modules.html#modules_modules_commonjs_modules
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import
https://developer.mozilla.org/en-US/docs/web/javascript/reference/statements/export

[[software.frameworks.js.node.module-system.require-function]]
[[software.frameworks.js.node.module-system.http-requests]]

