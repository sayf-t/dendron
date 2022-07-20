---
id: oqvos1vq9b8z908g964sbwe
title: Memory Calldata Storage
desc: ''
updated: 1658208946193
created: 1658208693236
---

There are 3 keywords for the data location for variables...

![](./assets/images/solidity-memory1.png)

... Needed for reference types like **strings, structs, arrays and mappings**
- whatever is declared as the data location, it will have an impact in the way data is copied
- eg a calldata item is saved to a state variable