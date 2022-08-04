---
id: 2ntzifl2dqe6ewed3tk5luh
title: Type Aliases
desc: ''
updated: 1659091592133
created: 1659091581339
---

```ts

type Employee = {
  readonly id: number;
  name: string;
  retire: (date: Date) => void;
};

let employee: Employee = {
  id: 1,
  name: "Syftr",
  retire: (date: Date) => {
    console.log(date);
  },
};

```