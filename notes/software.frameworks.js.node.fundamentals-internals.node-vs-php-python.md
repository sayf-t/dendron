---
id: 3zz7movln7d4ch00lnqtdmj
title: Node Vs PHP Python
desc: ''
updated: 1658050372685
created: 1658049695447
---

- Just like JS, Python and Java are also single-threaded.
- Traditionally Python and Java needed a webserver like Apache to handle requests eg some data. But these were blocking code, and would require another thread in Apache for the next request, and so on.
- Each client talking to the server would get its own thread - so the server would require a lot of resources!
- The server would only be able to handle as many connections as it could threads - not ideal for sites with millions of users - it was expensive!
- In 2009, Node became popular because of its non-blocking I/O
- Requests -> v8 engine -> libuv -> queues it up on event loop -> node can handle thousands of concurrent requests by passing this work off to the multiple threads in the threadpool
- where possible skipping the threadpool and talking to the operating system (multi threaded) , without blocking the server
- all this happens in the node.js process - no need for additional server to create thousands of threads.
- For many connections at the same time, Node's I/O model works really well.
- Python now has integrated support for running an event loop like node.
- But not as easy to deal with async programming as Node - it was specifically built for non-blocking I/O!
- Another server like NGINX can handle larger and more complex operations - but it depends on what you are building.

## When is it best to use Node? Why choose it?
- When computer reads from file, or makes requests over network - CPU not working very hard (the network card/hard drive are!)
- Node code sends code to our OS through the JS engine and libuv - its our OS that communicates at the lowest level to the CPU (machine code)
- The CPU will delegate tasks to devices over a communication channel called a `BUS`.
- More optimised in certain situations - Node is not great at video processing or ML.
- These are blocking, processor heavy computations on CPU or GPU.
- Node won't give many advantages over other languages/runtimes - but its GREAT at servers
- Like talking to databases and coordinating with other servers and services eg email and authentication
- Node works well when main performance problem is input/output rather than heavy calculations
- better to delegate these tasks to OS and devices on our computer
- If code gets blocked, or heavy CPU usage, the event loop will get stuck, and node won't handle other tasks efficiently
- Node is GREAT at serving data in I/O heavy applications. Eg video streaming at Netflix is mainly I/O. This is how Netflix works - with Node.js!
