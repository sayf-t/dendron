---
id: dkh53zesv4hziqikginhee2
title: Union Types
desc: ''
updated: 1659092033112
created: 1659091782536
---

```ts

function kgToLbs(weight: number | string) : number {
  // Narrowing
  if (typeOf weight === 'number') 
    return weight * 2.2;
  else 
    return parseInt(weight) * 2.2;
}

kgToLbs(10);
kgToLbs('10kg')

```