# Express.js JSON Body Parsing Issue

This repository demonstrates a common issue encountered when using custom middleware in Express.js applications. The problem occurs when attempting to parse JSON request bodies after applying a custom middleware function before `express.json()`. The `express.json()` middleware needs to be placed before any middleware that tries to access the request body.

## Bug Description

The provided code snippet shows an Express.js application that attempts to log the request body using `req.body`. However, when a custom middleware is placed before `express.json()`, `req.body` remains undefined, resulting in unexpected behavior and potential errors. This occurs because the JSON body parsing hasn't happened yet.

## Solution

The solution involves ensuring that `express.json()` is used before any middleware that accesses `req.body`.