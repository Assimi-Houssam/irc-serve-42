# IRC Server

**IRC Server** is a custom-built Internet Relay Chat (IRC) Server developed in C++ . It strictly use  to the IRC protocol (RFC 1459 / RFC 2812), allowing it to interface seamlessly with any standard IRC client (like HexChat).
> The core challenge lies in managing low-level network communication via sockets while simultaneously parsing complex command structures to handle multiple users, channels, and administrative privileges in real-time.

## The Architecture
To handle hundreds of simultaneous connections without blocking the server, the project uses a non-blocking I/O model. Established via the socket, bind, listen, and accept system calls.The server monitors all active file descriptors (clients) at once, only processing those that have sent data.
Each client has a dedicated buffer to handle partial messages, ensuring command integrity even over unstable connections.

The server functions as a "protocol translator," receiving raw text strings and converting them into logical chat actions.

## Tech Stack

Language: C++ (Standard 98 specific 42 requirements).

```
make
# Usage: ./ircserv <port> <password>
./ircserv 6667 my_secret_password
```

Connect a client: Open HexChat or your terminal, and connect to localhost:6667 with the password provided.

_From raw sockets to small talk: teaching machines to gossip like humans._
