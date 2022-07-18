---
id: q1r7ep6yc03j2kr529vyqm5
title: Event Loop
desc: ''
updated: 1658048269107
created: 1658047600122
---

# Why is it important?
- The event loop handles all the callback functions which help Node execute code asynchronously
- Allows programs to do multiple things all at once despite JS being a single threaded language
- When executing a program using the node runtime, a piece of code starts running
- it is a loop inside `libuv` - the EVENT LOOP
- This event loop is code that looks like:
```js

while(!shouldExit) {
  processEvents();
}

// Our loop checks if code is done executing
// And if the node process should exit
// If not, it processes all the events/callback functions that are called by the node program
// If no events, the function waits until there is one, it waits until your program triggers one of those callback functions
// passes off any work to OS or threadpool
// When done processing all the events it currently has
// It will start all over again

```
- The actual code lives in `libuv` and is executed in the C-language

## How does node process events? see [[software.frameworks.js.node.fundamentals-internals.callback-queues]]