---
id: c58xv1fqlvz4d93l3rrlh73
title: Intersection
desc: ''
updated: 1659092403808
created: 1659092197850
---


A number & a string at the same time?!
Not quite...

```ts
// let weight: number & string;

// new custom type
type Draggable = {
  drag: () => void
};

type Resizable = {
  resize: () => void
};

// intersection type
type UIWidget = Draggable & Resizable;

let textBox: UIWidget = {
  drag: () => {},
  resize: () => {}
}

```