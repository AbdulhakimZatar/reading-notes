# Message Queues

## Review, Research, and Discussion
* What does it mean that web sockets are bidirectional? Why is this useful?

An important consequence is that you may efficiently push data from the server to the client.

* Does socket.io use HTTP? Why?

Yes, the initial connection setup it done over HTTP. Also, a socket.io server will attach to an HTTP server so it can serve its own client code through /socket.io/socket.io.js .

* What happens when a client emits an event?
It send the payload to server

* What happens when a server emits an event?
It send it to all clients

* What happens if a client “misses” an event?
Nothing.


## Document the following Vocabulary Terms
* **Web Socket**:  computer communications protocol, providing full-duplex communication channels over a single TCP connection.
* **Socket.io**: JavaScript library for realtime web applications.
* **Client**:  piece of computer hardware or software that accesses a service made available by a server as part of the client–server model of computer networks. 
* **Server**: piece of computer hardware or software that provides functionality for other programs or devices, called "clients". 

## Preparation Materials

### Socket.io Chat Example

```
npm install express@4.15.2
```

```js
var app = require('express')();
var http = require('http').createServer(app);

app.get('/', (req, res) => {
  res.send('<h1>Hello world</h1>');
});

http.listen(3000, () => {
  console.log('listening on *:3000');
});
```

* Express initializes app to be a function handler that you can supply to an HTTP server (as seen in line 2).
* We define a route handler / that gets called when we hit our website home.
* We make the http server listen on port 3000.

#### Serving HTML
```js
app.get('/', (req, res) => {
  res.sendFile(__dirname + '/index.html');
});
```

```html
<!doctype html>
<html>
  <head>
    <title>Socket.IO chat</title>
    <style>
      * { margin: 0; padding: 0; box-sizing: border-box; }
      body { font: 13px Helvetica, Arial; }
      form { background: #000; padding: 3px; position: fixed; bottom: 0; width: 100%; }
      form input { border: 0; padding: 10px; width: 90%; margin-right: 0.5%; }
      form button { width: 9%; background: rgb(130, 224, 255); border: none; padding: 10px; }
      #messages { list-style-type: none; margin: 0; padding: 0; }
      #messages li { padding: 5px 10px; }
      #messages li:nth-child(odd) { background: #eee; }
    </style>
  </head>
  <body>
    <ul id="messages"></ul>
    <form action="">
      <input id="m" autocomplete="off" /><button>Send</button>
    </form>
  </body>
</html>
```

#### Integrating Socket.IO

```
npm install socket.io

```

```js
var app = require('express')();
var http = require('http').createServer(app);
var io = require('socket.io')(http);

app.get('/', (req, res) => {
  res.sendFile(__dirname + '/index.html');
});

io.on('connection', (socket) => {
  console.log('a user connected');
});

http.listen(3000, () => {
  console.log('listening on *:3000');
});
```

```html
<script src="/socket.io/socket.io.js"></script>
<script>
  var socket = io();
</script>
```

```js
io.on('connection', (socket) => {
  console.log('a user connected');
  socket.on('disconnect', () => {
    console.log('user disconnected');
  });
});
```

#### Emitting events
```html
<script src="/socket.io/socket.io.js"></script>
<script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>
<script>
  $(function () {
    var socket = io();
    $('form').submit(function(e) {
      e.preventDefault(); // prevents page reloading
      socket.emit('chat message', $('#m').val());
      $('#m').val('');
      return false;
    });
  });
</script>
```

```js
io.on('connection', (socket) => {
  socket.on('chat message', (msg) => {
    console.log('message: ' + msg);
  });
});
```

#### Broadcasting
```js
io.emit('some event', { someProperty: 'some value', otherProperty: 'other value' }); // This will emit the event to all connected sockets

io.on('connection', (socket) => {
  socket.broadcast.emit('hi');
});

io.on('connection', (socket) => {
  socket.on('chat message', (msg) => {
    io.emit('chat message', msg);
  });
});
```

```html
<script>
  $(function () {
    var socket = io();
    $('form').submit(function(e){
      e.preventDefault(); // prevents page reloading
      socket.emit('chat message', $('#m').val());
      $('#m').val('');
      return false;
    });
    socket.on('chat message', function(msg){
      $('#messages').append($('<li>').text(msg));
    });
  });
</script>
```

### Joining and leaving

```js
io.on('connection', socket => {
  socket.join('some room');
});
```

```js
io.to('some room').emit('some event');
io.to('room1').to('room2').to('room3').emit('some event');
```

```js
io.on('connection', function(socket){
  socket.to('some room').emit('some event');
});
```

#### Default room

```js
io.on('connection', socket => {
  socket.on('say to someone', (id, msg) => {
    socket.to(id).emit('my message', msg);
  });
});
```

#### Disconnection

```js
io.on('connection', socket => {
  socket.on('disconnecting', () => {
    const rooms = Object.keys(socket.rooms);
    // the rooms array contains at least the socket ID
  });

  socket.on('disconnect', () => {
    // socket.rooms === {}
  });
});
```

### emit cheatsheet

```js

io.on('connect', onConnect);

function onConnect(socket){

  // sending to the client
  socket.emit('hello', 'can you hear me?', 1, 2, 'abc');

  // sending to all clients except sender
  socket.broadcast.emit('broadcast', 'hello friends!');

  // sending to all clients in 'game' room except sender
  socket.to('game').emit('nice game', "let's play a game");

  // sending to all clients in 'game1' and/or in 'game2' room, except sender
  socket.to('game1').to('game2').emit('nice game', "let's play a game (too)");

  // sending to all clients in 'game' room, including sender
  io.in('game').emit('big-announcement', 'the game will start soon');

  // sending to all clients in namespace 'myNamespace', including sender
  io.of('myNamespace').emit('bigger-announcement', 'the tournament will start soon');

  // sending to a specific room in a specific namespace, including sender
  io.of('myNamespace').to('room').emit('event', 'message');

  // sending to individual socketid (private message)
  io.to(socketId).emit('hey', 'I just met you');

  // WARNING: `socket.to(socket.id).emit()` will NOT work, as it will send to everyone in the room
  // named `socket.id` but the sender. Please use the classic `socket.emit()` instead.

  // sending with acknowledgement
  socket.emit('question', 'do you think so?', function (answer) {});

  // sending without compression
  socket.compress(false).emit('uncompressed', "that's rough");

  // sending a message that might be dropped if the client is not ready to receive messages
  socket.volatile.emit('maybe', 'do you really need it?');

  // specifying whether the data to send has binary data
  socket.binary(false).emit('what', 'I have no binaries!');

  // sending to all clients on this node (when using multiple nodes)
  io.local.emit('hi', 'my lovely babies');

  // sending to all connected clients
  io.emit('an event sent to all connected clients');

};
```