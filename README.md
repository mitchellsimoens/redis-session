Node.JS Redis Session
=====================

This Node.JS module will handle saving session data into Redis without the use of cookies. This was done because iOS 5 disabled cookies by default causing issues with sessions that use cookies. This also doesn't have a dependancy on Connect or Express, just Redis.

Installation
------------

    npm install redis-session

Usage
-----

    var session = require('redis-session')();

Configuration
-------------

Here are the default configuration items:

* ttl        - The time to live for the session in milliseconds, defaults to 30000
* debug      - true to enable debug mode, defaults to false
* sidLength  - The number of characters to create the session ID, defaults to 40
* persist    - true to not allow the session to expire, defaults to false
* connection - An object to configure connection to Redis, defaults to { port : '6379', host : '127.0.0.1' }

To change the configuration items, you can do this:

    var session = require('redis-session')({
        debug : true,
        ttl   : 900000
    });