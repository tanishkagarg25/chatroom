# chatroom

This is a Python program that implements a basic chat application using sockets and threading. It consists of two parts, the client and the server.

The client creates a socket object and connects to the server's socket using the server's IP address and port number. It then prompts the user to choose an alias and starts two threads, one for receiving messages and another for sending messages. The receive thread continuously listens for messages from the server, and when it receives a message, it checks if it is an alias request. If it is, it sends the alias to the server; otherwise, it prints the message. The send thread prompts the user to enter a message and sends it to the server.

The server creates a socket object and binds it to its IP address and port number. It then listens for incoming connections from clients. When a client connects, it sends an alias request to the client and waits for the client to respond with an alias. Once it receives an alias, it adds the client's socket and alias to their respective lists and starts a new thread to handle the client's messages. The handle_client function listens for messages from the client and broadcasts them to all other clients. If the client disconnects, the handle_client function removes the client's socket and alias from the lists and broadcasts a message to all other clients that the client has left the chat room.

Overall, the program provides a basic implementation of a chat application that allows multiple clients to connect to a server and communicate with each other. However, it lacks several features such as encryption, user authentication, and message history, which could be added to improve the security and usability of the application.
