# Readings: Message-Queues

## Review, Research, and Discussion

1. #### What does it mean that web sockets are bidirectional? Why is this useful?

   This means that you can send and receieve between the server and the client. This enables the server to send real-time updates asynchronously, without requiring the client to submit a request each time.

2. #### Does socket.io use HTTP? Why?

   No it uses TCP protocol, as TCP allows a continous packets exchange.

3. #### What happens when a client emits an event?

   The event gets passed to the server through websockets. and the server will always be lisntening to the events.

4. #### What happens when a server emits an event?

   When a server emits an event, all connected clients will be notified.

## Vocabulary & Terms

| Term       | Defenition                                                                                                                                                                     |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Socket     | Sockets allow communication between two different processes on the same or different machines. To be more precise, it's a way to talk to other computers                       |
| Web Socket | WebSocket is bidirectional, a full-duplex protocol that is used in the same scenario of client-server communication                                                            |
| Socket.io  | JavaScript library for realtime web applications. It enables realtime, bi-directional communication between web clients and servers.                                           |
| Client     | In computing, a client is a piece of computer hardware or software that accesses a service made available by a server as part of the client–server model of computer networks. |
| Server     | The server is often on another computer system, in which case the client accesses the service by way of a network.                                                             |

| Packets | In networking, a packet is a small segment of a larger message. Data sent over computer networks\*, such as the Internet, is divided into packets. These packets are then recombined by the computer or device that receives them. |
