# Simple Java HTTP Server

## Overview
This is a simple HTTP server implemented in Java using `ServerSocket`. The server listens for incoming connections on port `8080` and responds to different requests based on the requested resource.

## Features
- Serves text responses for specific routes.
- Serves images when requested.
- Handles invalid or unknown requests gracefully.

## Requirements
- Java 8 or later
- An image named `download.jpg` in the project directory
- An image named `kaustav.jpg` in the project directory

## Installation & Usage
### 1. Compile the Server
```sh
javac Server.java
```

### 2. Run the Server
```sh
java Server
```
The server will start and listen on port `8080`.

### 3. Access the Server
Open a browser or use `curl` to send requests:

#### Retrieve a simple text response:
```sh
curl http://localhost:8080/hello
```
**Response:**
```
Hello World
```

#### Retrieve an image (`download.jpg`):
```sh
curl http://localhost:8080/cow --output cow.jpg
```

#### Retrieve another image (`kaustav.jpg`):
```sh
curl http://localhost:8080/kaustav --output kaustav.jpg
```

#### Test an unknown route:
```sh
curl http://localhost:8080/unknown
```
**Response:**
```
What ya lookin' for?
```

## How It Works
1. The server starts and listens on port `8080`.
2. When a client connects, it reads the incoming request.
3. The server parses the request to determine the requested resource.
4. Based on the requested resource:
   - If `/cow` is requested, it serves `download.jpg`.
   - If `/kaustav` is requested, it serves `kaustav.jpg`.
   - If `/hello` is requested, it responds with "Hello World".
   - For any other request, it responds with "What ya lookin' for?".
5. The server then closes the connection and waits for new requests.

## Notes
- Ensure `download.jpg` and `kaustav.jpg` exist in the same directory as the server.
- The server currently serves static responses and does not support advanced HTTP methods like `POST` or `PUT`.

## Future Improvements
- Add support for `POST` requests.
- Serve more types of files dynamically.
- Improve error handling and logging.
- Implement multi-threading to handle multiple requests concurrently.

## License
This project is free to use and modify.

---

Enjoy using your simple Java web server! 🚀

