# Distributed Lab 1: Go Chat Server

In this lab you will build a simple client-server chat system. To start with,
you should follow the guide in this week's third Distributed Systems video to
practice sending and receiving messages -- you should write this code yourself,
and **not** use the templates in `client` and `server`, which are there for the second part
of the lab.

## Using the lab sheet

There are two ways to use the lab sheet, you can either:

- [create a new repo from this template](https://github.com/UoB-CSA/distributed-lab-1/generate) - **this is the recommended way**
- download a [zip file](https://github.com/UoB-CSA/distributed-lab-1/archive/master.zip)

## Ratings

Each question is rated to help you balance your work:

- :red_circle::white_circle::white_circle::white_circle::white_circle: - Easy, strictly necessary.
- :red_circle::red_circle::white_circle::white_circle::white_circle: - Medium, still necessary.
- :red_circle::red_circle::red_circle::white_circle::white_circle: - Hard, necessary if you're aiming for higher marks.
- :red_circle::red_circle::red_circle::red_circle::white_circle: - Hard, useful for coursework extensions.
- :red_circle::red_circle::red_circle::red_circle::red_circle: - Hard, beyond what you need for any part of the coursework.

## Part 1: Simple Client-Server Message-Passing :red_circle::white_circle::white_circle::white_circle::white_circle:

Follow the [video](https://web.microsoftstream.com/video/1b5b7c56-7bbd-4626-8ef9-7bac57d0cb70), creating a simple client and server that can send messages to
each other. This is best tackled in stages. Again, you should write this code
from scratch, as this part of the lab does not relate to the code in `client` and `server`.  You
may want to look at the [net package](https://golang.org/pkg/net/) for parts of
this.

+ Stage 1: Achieve client-server interaction, with a server that listens for a
single message and then prints it out and terminates, and a client that dials
for a connection and sends a single message.

+ Stage 2: Modify the server so that it persists and handles new connections,
printing out messages from any clients that connect.

+ Stage 3: Modify the client so it can send user-defined messages.

+ Stage 4: Modify both components so that the server sends replies to the
client, which handles and displays them.

+ Stage 5: Create a fully interactive client-server loop, with the user prompted
for input which is sent to the server and then acknowledged back to the client,
without either component exiting or closing the connection.

## Part 2: Chat Server :red_circle::red_circle::white_circle::white_circle::white_circle:

Using what you have learned so far on the course, fill out the `client` and `server` skeleton code
to create a text-based chat system that handles multiple clients. 

The **client** needs to (a) process user input and send it to the server on each
newline; (b) _at the same time_, accept messages sent from the server and
display them as they arrive.

The **server** needs to (a) handle new clients connecting; (b) process incoming
messages from any connected client; (c) send any received message to all clients
_except_ the client that sent it.   

The real test of your code will be to communicate with two or more clients via
localhost, and see messages passing back and forth between them.

The skeleton code provides a starting point and some hints. You should use `go
run server.go` to run the server, and `go run client.go` to run the client.  The
server accepts a `-port` flag to define a port to listen on, and the client
accepts an `-ip` flag to define an ip:port string to connect to.  By default the
server launches on `:8030` and the client connects to that port on localhost.
