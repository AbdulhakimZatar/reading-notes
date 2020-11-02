# Socket.io

## Review, Research, and Discussion

* What is the benefit of transforming data into packets?

Packet switching with its supporting packet processing functions has several practical benefits over traditional circuit-switched networks

* UDP is often refereed to as a connectionless protocol. Why is this?

No connection needs to be established between the source and destination before you transmit data

* Can a socket server application have multiple socket connections?

Can share the same server-side IP/Port pair as long as they are associated with different client-side IP/Port pairs

* Can a socket connection application be connected to multiple socket servers?

Yes, you need a separate connection factory for each server/port.

* Can an application be both a socket server and a socket connection?

Yes, it can.

## Document the following Vocabulary Terms

* **OSI Model**: conceptual framework used to describe the functions of a networking system. 
* **TCP Model**: conceptual model and set of communications protocols used in the Internet and similar computer networks.
* **TCP**: one of the main protocols of the Internet protocol suite.
* **UDP**: communications protocol that is primarily used for establishing low-latency and loss-tolerating connections between applications on the internet.
* **Packets**: formatted unit of data carried by a packet-switched network.
* **Socket**: software structure within a network node of a computer network that serves as an endpoint for sending and receiving data across the network.

## Preparation Materials

### Web Sockets
WebSocket is distinct from HTTP. Both protocols are located at layer 7 in the OSI model and depend on TCP at layer 4. Although they are different, RFC 6455 states that WebSocket "is designed to work over HTTP ports 443 and 80 as well as to support HTTP proxies and intermediaries," thus making it compatible with the HTTP protocol. To achieve compatibility, the WebSocket handshake uses the HTTP Upgrade header[1] to change from the HTTP protocol to the WebSocket protocol.

### Socket.IO
Socket.IO enables real-time bidirectional event-based communication. It works on every platform, browser or device, focusing equally on reliability and speed. Socket.IO is built on top of the WebSockets API (Client side) and Node.js. It is one of the most depended upon library on npm (Node Package Manager).

### WebSocket vs Socket.io
**WebSocket** is the communication Protocol which provides bidirectional communication between the Client and the Server over a TCP connection, WebSocket remains open all the time so they allow the real-time data transfer. When clients trigger the request to the Server it does not close the connection on receiving the response, it rather persists and waits for Client or server to terminate the request.

**Socket.IO** is a library which enables real-time and full duplex communication between the Client and the Web servers. It uses the WebSocket protocol to provide the interface. Generally, it is divided into two parts, both WebSocket vs Socket.io are event-driven libraries

### How does that work?
The client will try to establish a WebSocket connection if possible, and will fall back on HTTP long polling if not.

WebSocket is a communication protocol which provides a full-duplex and low-latency channel between the server and the browser.

#### Server
```js
const io = require('socket.io')();
// or
const Server = require('socket.io');
const io = new Server();
```

#### Client
```js
<script src="/socket.io/socket.io.js"></script>
<script>
  const socket = io('http://localhost');
</script>
```

```js
const io = require('socket.io-client');
// or with import syntax
import io from 'socket.io-client';
```

#### Socket Testing Tool
[test](https://amritb.github.io/socketio-client-tool/)