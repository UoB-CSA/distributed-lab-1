# Go Chat Server

A simple client-server chat system. 

`go run server.go` to run the server, and `go run client.go` to run the client.
The server accepts a `-port` flag to define a port to listen on, and the client
accepts an `-ip` flag to define an ip:port string to connect to. By default the
server launches on `:8030` and the client connects to that port on localhost.
