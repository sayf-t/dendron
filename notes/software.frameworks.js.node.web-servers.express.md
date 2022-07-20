---
id: xg9wxnh85ph08f3i324h3k1
title: Express
desc: ''
updated: 1658200416180
created: 1658198825760
---

## Introduction
- Express is really good at:
  - routing!
  - setting content type

### Demo

```js

const express = require('express');

const app = express();

const PORT = 3000;

app.get('/', (req, res) => {
  res.send({
    id:1,
    name: "Sir Isaac Newton"
  });
});

app.get('/messages', (req, res) => {
  res.send('<h1>HELLO!</h1>');
});

app.post('/messages', (req, res) => {
  console.log('Updating messages...');
});

app.listen(PORT, () => {
  console.log(`Listening on ${PORT}`);
})

```
