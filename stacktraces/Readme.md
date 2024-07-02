# Panic Demo Web Server
This is a simple web server written in Go that demonstrates how to handle panics in a web application.

## Endpoints

The server has three endpoints:

* `/`: A simple "Hello!" page
* `/panic/`: Triggers a panic immediately
* `/panic-after/`: Writes a "Hello!" message to the response before triggering a panic

## Panic Handling

The server uses a custom middleware function `recoverMw` to catch and handle panics. When a panic occurs, the middleware logs the error and stack trace, and returns a 500 Internal Server Error response to the client. In development mode (i.e. when the `dev` parameter is `true`), the middleware also returns the panic error and stack trace as HTML.

## Running the Server

To run the server, simply execute the Go program:

```bash 
go run main.go
```

The server will listen on port 3000. You can access the endpoints using a web browser or a tool like `curl`.

## Notes

This server is for demonstration purposes only and should not be used in production without additional error handling and security measures.