---
id: doy599ewzdovg5p8avy2y0b
title: Async Callbacks
desc: ''
updated: 1658045463031
created: 1658032764880
---

## IS JS Asynchronous?
- out of the box, JS is synchronous.
- But we can write async code where we can execute a callback function in the future under certain conditions. Thus JS can behave in an async way.
- Things like `setTimeout()` are not JS native - thanks to libuv


### synchronous approach
```js
console.log('🐇 finishes!');
console.log('🐢 finishes!');
```
### async approach
```js
setTimeout(() => console.log('🐇 finishes!'), 1000);

console.log('🐢 finishes!');
```
- callbacks allow us to complete requests while running things separately
- You don't want to be caught off guard with a slow turtle winning a race unexpectedly


### Blocking Functions
Want to ensure that long-running functions are non-blocking, ensuring CPU stays awake.
- `JSON.stringify()`


### Non-blocking Functions
CPU is delegating work to other devices on computer such as network card or hard disk. CPU can be used more efficiently for other things.
- `setTimeout()`
- `makeRequest()`
- `readFile()`

