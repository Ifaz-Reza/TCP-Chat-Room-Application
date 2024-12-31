# TCP-Chat-Room-Application

This repository contains a simple TCP-based chat room application implemented in Java. The chat room allows multiple clients to connect to a server and communicate with each other in real-time. Each client can send messages, set nicknames, and leave the chat room using specific commands.

## Features

### Server
- Listens for incoming connections from clients on port `9999`.
- Handles multiple clients concurrently using threads.
- Broadcasts messages from one client to all connected clients.
- Allows clients to change their nicknames.
- Automatically notifies all clients when a user joins, changes their nickname, or leaves the chat.

### Client
- Connects to the server on `127.0.0.1:9999`.
- Sends and receives messages in real-time.
- Allows nickname changes using the `/nick` command.
- Exits the chat room using the `/quit` command.

## How It Works

### Server
1. Starts a server socket on port `9999`.
2. Accepts incoming client connections.
3. Each client connection is handled by a `ConnectionHandler` running on a separate thread.
4. Messages from clients are broadcast to all connected clients.

### Client
1. Connects to the server at `127.0.0.1:9999`.
2. Prompts the user for a nickname upon connection.
3. Sends user input to the server.
4. Receives and displays messages from the server.

## Commands
- **/nick [new_nickname]:** Changes the client's nickname.
- **/quit:** Disconnects the client from the server.

## Requirements
- Java Development Kit (JDK) 8 or higher.

## Setup and Usage

### Server
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd tcp-chat-room
   ```
2. Compile the server:
   ```bash
   javac Server.java
   ```
3. Run the server:
   ```bash
   java Server
   ```

### Client
1. Open a new terminal for each client.
2. Compile the client:
   ```bash
   javac Client.java
   ```
3. Run the client:
   ```bash
   java Client
   ```
4. Follow the prompts to set your nickname and start chatting!

## Example
### Server
```bash
java Server
```
Output:
```
Client1 connected!
Client2 connected!
Client1: Hello everyone!
Client2: Hi, Client1!
```

### Client
```bash
java Client
```
Output:
```
Please enter a nickname: Client1
Hello everyone!
```

### Commands Example
Client1:
```
/nick NewClient1
Successfully changed nickname to: NewClient1
```
Client2:
```
Hi, NewClient1!
/quit
```

## Notes
- Ensure the server is running before starting any clients.
- Clients must connect to the server on the same network.
- Use `/quit` to safely disconnect from the chat.

## License
This project is licensed under the MIT License. Feel free to use, modify, and distribute it.

## Contributing
Contributions are welcome! Feel free to submit issues or pull requests to improve the project.

## Author
Ifaz Reza
