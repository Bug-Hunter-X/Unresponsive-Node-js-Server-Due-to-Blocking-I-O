# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js applications where a long-running synchronous operation blocks the event loop, causing the server to become unresponsive to new requests.  The `blockingServer.js` file shows the problematic code, while `nonBlockingServer.js` provides a solution using asynchronous operations.

## Problem

Node.js is single-threaded and relies on its event loop to handle requests.  If a request handler performs a long-running synchronous operation (like a complex computation or I/O operation that doesn't use callbacks or promises), it blocks the event loop, preventing any other requests from being processed until the operation completes. This can lead to an unresponsive server and poor performance.

## Solution

The solution involves using asynchronous operations to avoid blocking the event loop.  This allows Node.js to continue handling other requests while the long-running operation is in progress.  Common approaches include using callbacks, promises, or async/await.