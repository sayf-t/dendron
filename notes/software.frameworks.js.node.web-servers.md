---
id: q01nh0oo5r25q6e2jjuzp84
title: Web Servers
desc: ''
updated: 1658198510353
created: 1658188611354
---

## What is a backend/HTTP server?
- when typing in an address to a browser
- your browser talks to a DNS
- DNS speaks to other DNS' to figure out where site lives
- Requests are made
- DNS cache might save some work and improve performance, users only need to request once

## HTTP responses and requests
- Browser speaks HTTP to the server and vice versa 
- possible actions one might want to perform: https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods
- GET / POST / PUT / DELETE ... etc
- Requests: Method, Path, Body, Headers
  - Header required is `Host` to verify message being sent to server
- Responses: Headers, Body, Status Code


## Demo - simple requests get quite complicated when we need to parse data...

```js

const http = require('http');

const PORT = 3000;

const server = http.createServer();

// parameterised endpoint/route
const friends = [
  {
    id: 0,
    name: "Nikola Tesla"
  },
  {
    id: 1,
    name: "Albert Einstein"
  },
  {
    id: 2,
    name: "Isaac Newton"
  },
]

server.on('request', (req, res) => { // req is a readable stream! res is a writeable stream!
  const items = req.url.split('/')
  // /friends/2 => ['', 'friends', '2']
  if (req.method === 'POST' && items[1] === 'friends') {
    req.on('data', (data) => { // handle 'data' event from the request object picked up in the request stream.
    // data received by server from browser => received as buffer => convert to string => convert to an object to add to our list of friends
      const friend = data.toString();
      console.log('Request:', friend);
      friends.push(JSON.parse(friend));
      // req.pipe(res); This is piping an incomplete response!
    });
    req.pipe(res); // it should be here instead
  } else if(req.method === 'GET' && items[1] === 'friends') {
    // res.writeHead(200, {
    //   // 'Content-Type': 'text/plain',
    //   'Content-Type': 'application/json',
    // });
    res.statusCode = 200;
    res.setHeader('Content-Type', 'application/json')
    if (items.length === 3) {
      const friendIndex = Number(items[2]);
      res.end(JSON.stringify(friends[friendIndex]))
      } else {
      res.end(JSON.stringify(friends));
    }
  } else if (req.method === 'GET' && items[1] === 'messages'){
      res.write('<html>')
      res.write('<body>')
      res.write('<ul>')
      res.write('<li>Hello Isaac!</li>')
      res.write('<li>What are your thoughts on astronomy?</li>')
      res.write('</ul>')
      res.write('</body>')
      res.write('</html>')
  } else {
      res.statusCode = 404;
      res.end();
  }
});

server.listen(PORT, () => {
  console.log(`Listening on port ${PORT}`);
}); // 127.0.0.1 => localhost

```

sample POST-request in browser
```js
fetch('http://localhost:3000/friends', {
  method: 'POST',
  body: JSON.stringify({ id: 3, name: 'Ryan Dahl'})
})
.then((response) => response.json())
.then((friend) => console.log(friend));

```


## Same Origin Policy
- A security feature to restrict where a browser can make requests to
- google.com cannot risk data with facebook.com
- need to protect users
  - exception: write requests
- An origin is a defined Protocol / Host / Port
eg 
- Protocol: ` https://`
- Host: `www.google.com/maps/`
- Port: `www.google.com:443/maps/`