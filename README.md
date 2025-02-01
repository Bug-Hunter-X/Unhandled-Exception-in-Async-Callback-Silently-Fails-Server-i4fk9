# Unhandled Exception in Async Callback Silently Fails Server

This repository demonstrates a common, yet subtle bug in Node.js applications where unhandled exceptions within asynchronous callbacks can lead to silent server failures.  The server continues running but fails to respond correctly, making debugging challenging.

## The Problem
The `bug.js` file shows a simple HTTP server that simulates an asynchronous operation.  Sometimes, this operation throws an exception.  However, because the exception is not handled within the asynchronous callback, it's not caught by the Node.js event loop, and the error is effectively swallowed, leading to silent failures. 

## The Solution
The `bugSolution.js` file demonstrates the corrected version. It uses a `try...catch` block to properly handle the exception, logging it to the console and providing a more informative response to the client.