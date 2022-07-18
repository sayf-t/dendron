---
id: mx7znimp56unp6lfrhqr7u7
title: Node Package Manager
desc: ''
updated: 1658137206551
created: 1658132812949
---

- A CLI tool downloaded when installing Node
- NPM bundled with node executable, creating central bundle of code
- Many packages shared by developers, and ecosystems of devs who share open source
- More learning materials and building blocks

## Creating our first NPM package
- module vs package
  - module is a file with code that may be exported
  - package is a collection of modules that are packaged together
- need to first run `npm init -y`
- you will get a `package.json` file
- can add scripts setting it to a command that will run applications, eg: `"start": "node https.js"` and run `npm run start` or `npm start` in the terminal command line to run the start script.

## Packages and the NPM Registry
- package means a re-usable package that has been shared on the registry

## Using 3rd Party Modules
`npm init -y`
`npm i axios`
- this downloads the axios code into the folder `node_modules`
- this modifies the `package.json` to keep track of the axios library as a project dependency - as well as in the `package-lock.json`
`touch request.js`

request.js
```js

const axios = require('axios');

axios.get('https://www.google.com')
  .then((response) => {
    console.log(response);
  })
  .catch((err) => console.log(err))
  .then(() => {
    console.log("All done!")
  });

  // as each promise gets resolved, the next callback runs

```

## Semantic Versioning
Version number MAJOR.MINOR.PATCH
- ensure no breaking changes upon minor version increase
- package authors need to be honest!

## Vulnerabilities in Dependencies
Security is a cat and mouse game where hackers find vulnerabilities and exploit weaknesses

### Links 


[[software.frameworks.js.node.node-package-manager.node-modules-folder]]
[[software.frameworks.js.node.node-package-manager.package-lock-json-versioning]]

npmjs.com