# Socket.io

Socket.IO is a library that enables low-latency, bidirectional and event-based communication between a client and a server.

### Real-time Applications

A real-time application (RTA) is an application that functions within a period that the user senses as immediate or current.

Some examples of real-time applications are:
Collaboration Applications, instant messengers and push Notifications.

## Why Socket.IO?

Writing a real-time application using popular web application stacks such as LAMP (PHP) has always been a difficult task. It entails polling the server for updates and keeping track of timestamps, and it runs far slower than it should.

Most real-time systems have typically been built on sockets, which provide a bi-directional communication channel between a client and a server. This indicates that the server has the ability to send messages to clients. The concept is that whenever an event occurs, the server will receive it and send it to the connected clients that are affected.

## Difference Between WebSocket and Socket.io

WebSocket is a communication protocol that allows bidirectional communication between a client and a server over a TCP connection. Because WebSockets are always open, they allow for real-time data transmission. When a client sends a request to a server, the server does not stop the connection after getting the response; instead, it lingers and waits for the client or server to end the request. Socket.IO is a library that allows clients and web servers to communicate in real time and in full duplex. The interface is provided by the WebSocket protocol. Both WebSocket and Socket.io are event-driven libraries, thus they're separated into two components.

### Key features of Socket.IO

- It helps in broadcasting to multiple sockets at a time and handles the connection transparently.
- It works on all platform, server or device, ensuring equality, reliability, and speed.
- It automatically upgrades the requirement to WebSocket if needed.
- It is a custom real-time transport protocol implementation on top of other protocols.
- It requires both libraries to be used Client side as well as a server-side library.
- IO works on work-based events. there are some reserved events that can be accessed using the Socket on the server side like Connect, message, Disconnect, Ping and Reconnect.
- There are some Client based reserved events like Connect, connect- error, connect-timeout and Reconnect etc.
