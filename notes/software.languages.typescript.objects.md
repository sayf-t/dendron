---
id: fa6f2ala0zhajj80zkso4y7
title: Objects
desc: ''
updated: 1659091649654
created: 1659091186751
---

Quite Verbose...
```ts
let employee: { 
  readonly id: number,
  name: string,
  retire: (date: Date) => void
} = { id: 1, name: 'Syftr', retire: (date: Date) => {
  console.log(date);
} };
```

Check out [[software.languages.typescript.type-aliases]] ! It helps with this in structuring objects in a DRY way!