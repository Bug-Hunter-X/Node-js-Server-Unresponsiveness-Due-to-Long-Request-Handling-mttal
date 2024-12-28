# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js servers: unresponsiveness due to long-running requests.  A poorly-handled long request can block the event loop, preventing the server from processing other requests.

## The Problem

The `bug.js` file contains a simple HTTP server that simulates a long-running request with a 5-second delay.  During this delay, the server is unable to accept or respond to other requests.  This can lead to poor performance and potentially a crash if many such requests are made concurrently.

## The Solution

The `bugSolution.js` file demonstrates a solution using worker threads to offload long-running tasks from the main event loop. This prevents the server from becoming unresponsive.

## How to Run

1. Clone the repository.
2. Navigate to the directory.
3. Run `node bug.js` to see the unresponsive behavior.
4. Run `node bugSolution.js` to see the improved responsiveness.

This example highlights the importance of asynchronous programming and worker threads for maintaining responsiveness in Node.js servers handling potentially slow or long-running operations.