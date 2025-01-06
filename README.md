# Node.js Server Hang Issue

This repository demonstrates a common Node.js issue where a long-running synchronous operation in the request handler blocks the event loop, causing the server to hang and become unresponsive.  The `server.js` file contains the problematic code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem

The original code uses a `while` loop to simulate a long-running task. This blocks the event loop, preventing the server from handling other requests or closing gracefully.  This is a classic example of how synchronous code can cripple Node.js's non-blocking, event-driven architecture.

## Solution

The solution involves refactoring the code to use asynchronous operations.  This allows the event loop to continue processing other events while the long-running task executes in the background.  Asynchronous approaches would typically involve using promises, async/await, or callbacks, preventing the main thread from being blocked.