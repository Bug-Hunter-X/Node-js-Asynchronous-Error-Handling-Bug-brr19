# Node.js Asynchronous Error Handling Bug

This repository demonstrates a common bug in Node.js applications involving asynchronous operations and improper error handling. The bug causes the server to sometimes return a 500 Internal Server Error, even though the code appears to handle errors correctly.

## Bug Description

The server simulates an asynchronous operation (using `setTimeout`) that randomly returns either a success or an error.  The error handling attempts to set the response code to 500, but this isn't sufficient for handling the error properly in all scenarios.

## Bug Solution

The solution introduces proper error handling using try-catch blocks and improves the clarity of error handling messages.  It also shows how to utilize a custom error handler, preventing unexpected errors from disrupting the operation of the server.

## How to Reproduce

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies (none required in this example).
4. Run `node bug.js` to start the server.
5. Send multiple requests to `http://localhost:3000` using a tool like `curl` or a web browser.
6. Observe that some requests result in a 500 error.