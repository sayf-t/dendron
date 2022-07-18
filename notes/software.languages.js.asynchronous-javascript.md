---
id: 751yjy42txvzunn49swsj87
title: Asynchronous JavaScript
desc: ''
updated: 1658104436983
created: 1658061839805
---

- Async = we don't have all the data currently

- JS is single-threaded

- Async functions are functions we can execute later

## What are Promises?
- Definition: A promise is an object that may produce a single value some time in the future
- Either a resolved value, or a reason that it's not resolved (rejected)
- Promise is in one of three states: fulfilled, rejected or pending
- Promises can only succeed or fail once

### Demo
```js
const promise = new Promise((res, rej) => {
    if (true) {
        throw Error
        res('Stuff Worked');
    } else {
        rej('Error, it broke');
    }
})
.catch(() => console.log('error!'))

//A promise is something you can have currently to not block the execution of the code - the task happens in the background
// It either gets fulfilled or rejected
```