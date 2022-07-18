---
id: ypipllsqsn3409a2alxt265
title: Async Await
desc: ''
updated: 1658107357587
created: 1658104586835
---

- Built on top of promises
- Benefit is that it makes async functions easier to read

```js

movePlayer(100, 'Left')
.then(() => movePlayer(100, 'Left'))
.then(() => movePlayer(10, 'Right'))
.then(() => movePlayer(330, 'Left'))

//becomes

async function playerStart() {
  const result = await movePlayer(100, 'Left');  
  const result2 = await movePlayer(10, 'Right');  
}

// example 2

async function fetchUsers() {
  const resp = await fetch('https://...');
  const data = await resp.json();
  console.log(data);
}

// example 3

const promisify = (item, delay) =>
  new Promise((resolve) =>
    setTimeout(() =>
      resolve(item), delay));

const a = () => promisify('a', 100);
const b = () => promisify('b', 5000);
const c = () => promisify('c', 3000);

async function parallel() {
  const promises = [a(), b(), c()];
  const [output1, output2, output3] = await Promise.all(promises);
  return `parallel is done: ${output1} ${output2} ${output3}`
}

async function race() {
  const promises = [a(), b(), c()];
  const output1 = await Promise.race(promises);
  return `race is done: ${output1}`;
}

async function sequence() {
  const output1 = await a();
  const output2 = await b();
  const output3 = await c();
  return `sequence is done ${output1} ${output2} ${output3}`
}


parallel().then(console.log)
sequence().then(console.log)
race().then(console.log)
```