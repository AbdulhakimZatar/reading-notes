# TCP Servers

## Review, Research, and Discussion

* Given the examples of front-end events such as button click, window resize, form submit, etc, what are some examples of back-end * events?

 Freshdesk product events such as ticket create, ticket update, and note create that trigger backend app.

* Why are events sometimes better than asynchronous actions with callbacks?

An event handler is a type of callback. It's called whenever an event occurs. The term is usually used in terms of user interfaces where events are things like moving the mouse, clicking something and so on.

* What does an EventEmitter instance do?

All objects that emit events are instances of the EventEmitter class. These objects expose an eventEmitter.

* When is a program’s call stack, event queue, and event loop active?

The main event loop is the one that is running on the main thread, it is the only active event loop when the application starts, and it remains active until the application ends.

having one is to keep track of the point to which each active subroutine should return control when it finishes executing.


## Document the following Vocabulary Terms

* **Observer Pattern**: software design pattern in which an object, called the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods.
* **Listener**: must implement the interface for the event it wants to listen to 
* **Event Handler**: software routine that processes actions such as keystrokes and mouse movements.
* **Event Driven Programming**: programming paradigm in which the flow of the program is determined by events such as user actions, sensor outputs, or messages from other programs or threads.
* **Event Loop**: programming construct or design pattern that waits for and dispatches events or messages in a program.
* **Event Queue**: repository where events from an application are held prior to being processed by a receiving program or system.
* **Call Stack**:  stack data structure that stores information about the active subroutines of a computer program.
* **Emit/Raise/Trigger**: function raises the specified event.
* **Subscribe**:  one where providers that supply not only network access and a foundation suite of applications, but also the complete user environment—including all customer premises equipment—as a package for a monthly subscription.
* **database**: data structure that stores organized information.

## Preparation Materials

### OSI Model

#### What is the OSI model?
The Open Systems Interconnection (OSI) model is a conceptual model created by the International Organization for Standardization which enables diverse communication systems to communicate using standard protocols. In plain English, the OSI provides a standard for different computer systems to be able to communicate with each other.
![ex](https://www.cloudflare.com/img/learning/ddos/what-is-a-ddos-attack/osi-model-7-layers.svg)

Each layer of the OSI model handles a specific job and communicates with the layers above and below itself. DDoS attacks target specific layers of a network connection; application layer attacks target layer 7 and protocol layer attacks target layers 3 and 4.

#### Why does the OSI model matter?
Although the modern Internet doesn’t strictly follow the OSI model (it more closely follows the simpler Internet protocol suite), the OSI model is still very useful for troubleshooting network problems. Whether it’s one person who can’t get their laptop on the Internet, or a web site being down for thousands of users, the OSI model can help to break down the problem and isolate the source of the trouble. If the problem can be narrowed down to one specific layer of the model, a lot of unnecessary work can be avoided.

### TCP
TCP (Transmission Control Protocol) is a standard that defines how to establish and maintain a network conversation through which application programs can exchange data. TCP works with the Internet Protocol (IP), which defines how computers send packets of data to each other. Together, TCP and IP are the basic rules defining the Internet. The Internet Engineering Task Force (IETF) defines TCP in the Request for Comment (RFC) standards document number 793.

#### How Transmission Control Protocol works
TCP is a connection-oriented protocol, which means a connection is established and maintained until the application programs at each end have finished exchanging messages. It determines how to break application data into packets that networks can deliver, sends packets to and accepts packets from the network layer, manages flow control and -- because it is meant to provide error-free data transmission -- handles retransmission of dropped or garbled packets and acknowledges all packets that arrive. In the Open Systems Interconnection (OSI) communication model, TCP covers parts of Layer 4, the transport layer, and parts of Layer 5, the session layer.
![ex](https://cdn.ttgtmedia.com/rms/onlineImages/networking-osi_vs_tcp-ip_model_table_desktop.jpg)

#### What TCP is used for
TCP is used for organizing data in a way that ensures the secure transmission between the server and client. It guarantees the integrity of data sent over the network, regardless of the amount. For this reason, it is used to transmit data from other higher-level protocols that require all transmitted data to arrive. Examples include:

* Secure Shell (SSH), File Transfer Protocol (FTP), Telnet: For peer-to-peer file sharing, and, in Telnet's case, logging into another user's computer to access a file.
* Simple Mail Transfer Protocol (SMTP), Post Office Protocol (POP), Internet Message Access Protocol (IMAP): For sending and receiving email
* HTTP: For web access

#### Why TCP is important
TCP is important because it establishes the rules and standard procedures for the way information is communicated over the internet. It is the foundation for the internet as it exists today and ensures that data transmission is carried out uniformly, regardless of the location, hardware or software involved. For this reason, it is flexible and highly scalable, meaning new protocols can be introduced to it and it will accommodate them. It is also nonproprietary, meaning no one person or company owns it.

### Build a TCP Server

#### TCP Server:
```js
var net = require('net');
 
// Configuration parameters
var HOST = 'localhost';
var PORT = 1234;
 
// Create Server instance 
var server = net.createServer(onClientConnected);  
 
server.listen(PORT, HOST, function() {  
  console.log('server listening on %j', server.address());
});
 
function onClientConnected(sock) {  
  var remoteAddress = sock.remoteAddress + ':' + sock.remotePort;
  console.log('new client connected: %s', remoteAddress);
 
  sock.on('data', function(data) {
    console.log('%s Says: %s', remoteAddress, data);
    sock.write(data);
    sock.write(' exit');
  });
  sock.on('close',  function () {
    console.log('connection from %s closed', remoteAddress);
  });
  sock.on('error', function (err) {
    console.log('Connection %s error: %s', remoteAddress, err.message);
  });
};
```

#### TCP Client:
```js
var net = require('net');
 
var HOST = 'localhost';
var PORT = 1234;
 
var client = new net.Socket();
 
client.connect(PORT, HOST, function() {
    console.log('Client connected to: ' + HOST + ':' + PORT);
    // Write a message to the socket as soon as the client is connected, the server will receive it as message from the client 
    client.write('Hello World!');
 
});
 
client.on('data', function(data) {    
    console.log('Client received: ' + data);
     if (data.toString().endsWith('exit')) {
       client.destroy();
    }
});
 
// Add a 'close' event handler for the client socket
client.on('close', function() {
    console.log('Client closed');
});
 
client.on('error', function(err) {
    console.error(err);
});
```

### Net
The net module provides an asynchronous network API for creating stream-based TCP or IPC servers (net.createServer()) and clients (net.createConnection()).

#### IPC support
The net module supports IPC with named pipes on Windows, and Unix domain sockets on other operating systems.

#### Identifying paths for IPC connections
net.connect(), net.createConnection(), server.listen() and socket.connect() take a path parameter to identify IPC endpoints.

