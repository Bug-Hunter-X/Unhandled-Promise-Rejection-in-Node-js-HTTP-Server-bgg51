# Unhandled Promise Rejection in Node.js HTTP Server

This repository demonstrates a common error in Node.js where an unhandled promise rejection in an asynchronous operation within an HTTP server leads to silent failures.  The server doesn't respond appropriately to errors, making it difficult to debug and resulting in a poor user experience.

## Problem

The `bug.js` file contains a Node.js HTTP server that performs an asynchronous operation (`doSomethingAsync`).  If this operation encounters an error, the error is logged to the console, but the HTTP request is not handled properly. This results in the client receiving no response.

## Solution

The `bugSolution.js` file demonstrates the correct way to handle asynchronous errors within an HTTP server. It uses a `try...catch` block to handle potential errors, ensuring that the client receives an appropriate error response.

## How to Reproduce

1. Clone the repository.
2. Run `node bug.js`.
3. Make several requests to `http://localhost:3000`. You will observe that sometimes, the server will not respond; it will simply hang and there will be an error in the server's console.
4. Run `node bugSolution.js` and repeat the requests.  The solution will respond with an error code whenever something goes wrong. 