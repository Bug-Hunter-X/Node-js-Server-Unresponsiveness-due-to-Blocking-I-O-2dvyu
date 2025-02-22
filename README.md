# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js servers: unresponsiveness caused by blocking the event loop with a long-running synchronous operation.

## Problem

The `server.js` file contains a simple HTTP server. However, the request handler includes a loop that simulates a computationally expensive task.  This loop runs synchronously, blocking the event loop and preventing the server from handling other requests.  As a result, the server becomes unresponsive and may appear to hang.

## Solution

The `serverSolution.js` file provides a solution using asynchronous operations (using `setTimeout`) or workers to avoid blocking the event loop and improve server responsiveness.

## How to reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node server.js`.  Try making multiple requests to `http://localhost:3000`. You'll observe that the server becomes slow to respond, or may not respond at all.
4. Run `node serverSolution.js`.  Make the same requests. You'll now see much better responsiveness.

This example highlights the importance of using asynchronous programming techniques (as demonstrated in `serverSolution.js`) in Node.js to prevent blocking the event loop and ensure server responsiveness.