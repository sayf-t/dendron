---
id: h1gv9dnt6gniv3b45orsieq
title: Tuples
desc: ''
updated: 1659089262069
created: 1659088877693
---

- New type which is a fixed length array, where each element is a particular type

![](./assets/images/typescript-tuples.png)

One instance where the compiler does not catch anything wrong
```ts
// 1, 'Mosh'
let user: [number, string] = [1, 'Mosh'];
user.push(5);

```