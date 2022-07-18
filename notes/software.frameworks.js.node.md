---
id: ogqav8welcflggpk205c5s0
title: Node
desc: ''
updated: 1658029218872
created: 1657943680420
---

## How do you run JavaScript?
- NEED A JS RUNTIME  
Usual process:
- write JS instructions
- feed it into an 'engine' which executes JS code <--- need a computer to understand JS
- our machines do something with those instructions
- Google introduced the v8 JS engine in 2008
  - fast, performant & great user experience
  - Node.js was born in 2009 (Ryan Dahl)

## What is a JS runtime?
- Not a programming language or framework
- It is a JS environment that allows us to run JS and do extra stuff
- `libuv` - is a library in C++ that combined with the V8 Engine
- Is a web browser a JS runtime? Yes, it implements call stack, heap and event loop; and has the `window` object

## What happens when you run `node` in the terminal?
- you get access to the REPL (read, eval, print & loop)
  - reading & parsing the code: the JS engine will break down our code and understand the different parts of it.
  - `undefined` means nothing is returned
- when you run node, you can run JS code
- not ideal to write large amounts of code - usually that is done in JS files in code editors

## What distinguishes the Chrome v8 engine from Node's?
- Chrome's browser comes with some features like the `window` object, within which sits items like `document object model` or DOM
- Node on the other hand has the `global` object (see more in [[global |software.frameworks.js.node.global-object]])

## Backend vs Frontend
- Language for Request/Response communications via HTTP
- Client-Server Architecture
- HTTPS is the secure version of this protocol
  - Data is secure and encrypted when being transferred over the internet; protected
- Backend serves data to client as:
  - JS/CSS/HTML
  - JSON
  - XML

## How are Backends made?
- Ruby / Node / C# / Java
- Benefit is to create backend and frontend in the same language

## [[Node.js Fundamentals: Internals |software.frameworks.js.node.fundamentals-internals]]