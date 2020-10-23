# zoom-clone-nodejs

[![Express Logo](https://i.cloudup.com/zfY6lL7eFa-3000x3000.png)](http://expressjs.com/)

  Fast, unopinionated, minimalist web framework for [node](http://nodejs.org).

  [![NPM Version][npm-image]][npm-url]
  [![NPM Downloads][downloads-image]][downloads-url]
  [![Linux Build][travis-image]][travis-url]
  [![Windows Build][appveyor-image]][appveyor-url]
  [![Test Coverage][coveralls-image]][coveralls-url]

```js
const express = require('express')
const app = express()

app.get('/', function (req, res) {
  res.send('Hello World')
})

app.listen(3000)
```

## Installation

This is a [Node.js](https://nodejs.org/en/) module available through the
[npm registry](https://www.npmjs.com/).

Before installing, [download and install Node.js](https://nodejs.org/en/download/).
Node.js 0.10 or higher is required.

Installation is done using the
[`npm install` command](https://docs.npmjs.com/getting-started/installing-npm-packages-locally):

```bash
$ npm install express
```

Follow [our installing guide](http://expressjs.com/en/starter/installing.html)
for more information.

## Features

  * Robust routing
  * Focus on high performance
  * Super-high test coverage
  * HTTP helpers (redirection, caching, etc)
  * View system supporting 14+ template engines
  * Content negotiation
  * Executable for generating applications quickly

## Docs & Community

  * [Website and Documentation](http://expressjs.com/) - [[website repo](https://github.com/expressjs/expressjs.com)]
  * [#express](https://webchat.freenode.net/?channels=express) on freenode IRC
  * [GitHub Organization](https://github.com/expressjs) for Official Middleware & Modules
  * Visit the [Wiki](https://github.com/expressjs/express/wiki)
  * [Google Group](https://groups.google.com/group/express-js) for discussion
  * [Gitter](https://gitter.im/expressjs/express) for support and discussion

**PROTIP** Be sure to read [Migrating from 3.x to 4.x](https://github.com/expressjs/express/wiki/Migrating-from-3.x-to-4.x) as well as [New features in 4.x](https://github.com/expressjs/express/wiki/New-features-in-4.x).

### Security Issues

If you discover a security vulnerability in Express, please see [Security Policies and Procedures](Security.md).

## Quick Start

  The quickest way to get started with express is to utilize the executable [`express(1)`](https://github.com/expressjs/generator) to generate an application as shown below:

  Install the executable. The executable's major version will match Express's:

```bash
$ npm install -g express-generator@4
```

  Create the app:

```bash
$ express /tmp/foo && cd /tmp/foo
```

  Install dependencies:

```bash
$ npm install
```

  Start the server:

```bash
$ npm start
```

  View the website at: http://localhost:3000

## Philosophy

  The Express philosophy is to provide small, robust tooling for HTTP servers, making
  it a great solution for single page applications, web sites, hybrids, or public
  HTTP APIs.

  Express does not force you to use any specific ORM or template engine. With support for over
  14 template engines via [Consolidate.js](https://github.com/tj/consolidate.js),
  you can quickly craft your perfect framework.

## Examples

  To view the examples, clone the Express repo and install the dependencies:

```bash
$ git clone git://github.com/expressjs/express.git --depth 1
$ cd express
$ npm install
```

  Then run whichever example you want:

```bash
$ node examples/content-negotiation
```

## Tests

  To run the test suite, first install the dependencies, then run `npm test`:

```bash
$ npm install
$ npm test
```

## Contributing

[Contributing Guide](Contributing.md)

## People

The original author of Express is [TJ Holowaychuk](https://github.com/tj)

The current lead maintainer is [Douglas Christopher Wilson](https://github.com/dougwilson)

[List of all contributors](https://github.com/expressjs/express/graphs/contributors)

## License

  [MIT](LICENSE)

[npm-image]: https://img.shields.io/npm/v/express.svg
[npm-url]: https://npmjs.org/package/express
[downloads-image]: https://img.shields.io/npm/dm/express.svg
[downloads-url]: https://npmjs.org/package/express
[travis-image]: https://img.shields.io/travis/expressjs/express/master.svg?label=linux
[travis-url]: https://travis-ci.org/expressjs/express
[appveyor-image]: https://img.shields.io/appveyor/ci/dougwilson/express/master.svg?label=windows
[appveyor-url]: https://ci.appveyor.com/project/dougwilson/express
[coveralls-image]: https://img.shields.io/coveralls/expressjs/express/master.svg
[coveralls-url]: https://coveralls.io/r/expressjs/express?branch=master




# socket.io

[![Backers on Open Collective](https://opencollective.com/socketio/backers/badge.svg)](#backers) [![Sponsors on Open Collective](https://opencollective.com/socketio/sponsors/badge.svg)](#sponsors)
[![Build Status](https://secure.travis-ci.org/socketio/socket.io.svg?branch=master)](https://travis-ci.org/socketio/socket.io)
[![Dependency Status](https://david-dm.org/socketio/socket.io.svg)](https://david-dm.org/socketio/socket.io)
[![devDependency Status](https://david-dm.org/socketio/socket.io/dev-status.svg)](https://david-dm.org/socketio/socket.io#info=devDependencies)
[![NPM version](https://badge.fury.io/js/socket.io.svg)](https://www.npmjs.com/package/socket.io)
![Downloads](https://img.shields.io/npm/dm/socket.io.svg?style=flat)
[![](https://slackin-socketio.now.sh/badge.svg)](https://slackin-socketio.now.sh)

## Features

Socket.IO enables real-time bidirectional event-based communication. It consists of:

- a Node.js server (this repository)
- a [Javascript client library](https://github.com/socketio/socket.io-client) for the browser (or a Node.js client)

Some implementations in other languages are also available:

- [Java](https://github.com/socketio/socket.io-client-java)
- [C++](https://github.com/socketio/socket.io-client-cpp)
- [Swift](https://github.com/socketio/socket.io-client-swift)
- [Dart](https://github.com/rikulo/socket.io-client-dart)

Its main features are:

#### Reliability

Connections are established even in the presence of:
  - proxies and load balancers.
  - personal firewall and antivirus software.

For this purpose, it relies on [Engine.IO](https://github.com/socketio/engine.io), which first establishes a long-polling connection, then tries to upgrade to better transports that are "tested" on the side, like WebSocket. Please see the [Goals](https://github.com/socketio/engine.io#goals) section for more information.

#### Auto-reconnection support

Unless instructed otherwise a disconnected client will try to reconnect forever, until the server is available again. Please see the available reconnection options [here](https://github.com/socketio/socket.io-client/blob/master/docs/API.md#new-managerurl-options).

#### Disconnection detection

A heartbeat mechanism is implemented at the Engine.IO level, allowing both the server and the client to know when the other one is not responding anymore.

That functionality is achieved with timers set on both the server and the client, with timeout values (the `pingInterval` and `pingTimeout` parameters) shared during the connection handshake. Those timers require any subsequent client calls to be directed to the same server, hence the `sticky-session` requirement when using multiples nodes.

#### Binary support

Any serializable data structures can be emitted, including:

- [ArrayBuffer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) and [Blob](https://developer.mozilla.org/en-US/docs/Web/API/Blob) in the browser
- [ArrayBuffer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) and [Buffer](https://nodejs.org/api/buffer.html) in Node.js

#### Simple and convenient API

Sample code:

```js
io.on('connection', socket => {
  socket.emit('request', /* … */); // emit an event to the socket
  io.emit('broadcast', /* … */); // emit an event to all connected sockets
  socket.on('reply', () => { /* … */ }); // listen to the event
});
```

#### Cross-browser

Browser support is tested in Saucelabs:

[![Sauce Test Status](https://saucelabs.com/browser-matrix/socket.svg)](https://saucelabs.com/u/socket)

#### Multiplexing support

In order to create separation of concerns within your application (for example per module, or based on permissions), Socket.IO allows you to create several `Namespaces`, which will act as separate communication channels but will share the same underlying connection.

#### Room support

Within each `Namespace`, you can define arbitrary channels, called `Rooms`, that sockets can join and leave. You can then broadcast to any given room, reaching every socket that has joined it.

This is a useful feature to send notifications to a group of users, or to a given user connected on several devices for example.


**Note:** Socket.IO is not a WebSocket implementation. Although Socket.IO indeed uses WebSocket as a transport when possible, it adds some metadata to each packet: the packet type, the namespace and the ack id when a message acknowledgement is needed. That is why a WebSocket client will not be able to successfully connect to a Socket.IO server, and a Socket.IO client will not be able to connect to a WebSocket server (like `ws://echo.websocket.org`) either. Please see the protocol specification [here](https://github.com/socketio/socket.io-protocol).

## Installation

```bash
npm install socket.io
```

## How to use

The following example attaches socket.io to a plain Node.JS
HTTP server listening on port `3000`.

```js
const server = require('http').createServer();
const io = require('socket.io')(server);
io.on('connection', client => {
  client.on('event', data => { /* … */ });
  client.on('disconnect', () => { /* … */ });
});
server.listen(3000);
```

### Standalone

```js
const io = require('socket.io')();
io.on('connection', client => { ... });
io.listen(3000);
```

### In conjunction with Express

Starting with **3.0**, express applications have become request handler
functions that you pass to `http` or `http` `Server` instances. You need
to pass the `Server` to `socket.io`, and not the express application
function. Also make sure to call `.listen` on the `server`, not the `app`.

```js
const app = require('express')();
const server = require('http').createServer(app);
const io = require('socket.io')(server);
io.on('connection', () => { /* … */ });
server.listen(3000);
```

### In conjunction with Koa

Like Express.JS, Koa works by exposing an application as a request
handler function, but only by calling the `callback` method.

```js
const app = require('koa')();
const server = require('http').createServer(app.callback());
const io = require('socket.io')(server);
io.on('connection', () => { /* … */ });
server.listen(3000);
```

## Documentation

Please see the documentation [here](/docs/README.md). Contributions are welcome!

## Debug / logging

Socket.IO is powered by [debug](https://github.com/visionmedia/debug).
In order to see all the debug output, run your app with the environment variable
`DEBUG` including the desired scope.

To see the output from all of Socket.IO's debugging scopes you can use:

```
DEBUG=socket.io* node myapp
```

## Testing

```
npm test
```
This runs the `gulp` task `test`. By default the test will be run with the source code in `lib` directory.

Set the environmental variable `TEST_VERSION` to `compat` to test the transpiled es5-compat version of the code.

The `gulp` task `test` will always transpile the source code into es5 and export to `dist` first before running the test.


## Backers

Support us with a monthly donation and help us continue our activities. [[Become a backer](https://opencollective.com/socketio#backer)]

<a href="https://opencollective.com/socketio/backer/0/website" target="_blank"><img src="https://opencollective.com/socketio/backer/0/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/1/website" target="_blank"><img src="https://opencollective.com/socketio/backer/1/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/2/website" target="_blank"><img src="https://opencollective.com/socketio/backer/2/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/3/website" target="_blank"><img src="https://opencollective.com/socketio/backer/3/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/4/website" target="_blank"><img src="https://opencollective.com/socketio/backer/4/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/5/website" target="_blank"><img src="https://opencollective.com/socketio/backer/5/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/6/website" target="_blank"><img src="https://opencollective.com/socketio/backer/6/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/7/website" target="_blank"><img src="https://opencollective.com/socketio/backer/7/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/8/website" target="_blank"><img src="https://opencollective.com/socketio/backer/8/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/9/website" target="_blank"><img src="https://opencollective.com/socketio/backer/9/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/10/website" target="_blank"><img src="https://opencollective.com/socketio/backer/10/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/11/website" target="_blank"><img src="https://opencollective.com/socketio/backer/11/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/12/website" target="_blank"><img src="https://opencollective.com/socketio/backer/12/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/13/website" target="_blank"><img src="https://opencollective.com/socketio/backer/13/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/14/website" target="_blank"><img src="https://opencollective.com/socketio/backer/14/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/15/website" target="_blank"><img src="https://opencollective.com/socketio/backer/15/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/16/website" target="_blank"><img src="https://opencollective.com/socketio/backer/16/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/17/website" target="_blank"><img src="https://opencollective.com/socketio/backer/17/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/18/website" target="_blank"><img src="https://opencollective.com/socketio/backer/18/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/19/website" target="_blank"><img src="https://opencollective.com/socketio/backer/19/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/20/website" target="_blank"><img src="https://opencollective.com/socketio/backer/20/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/21/website" target="_blank"><img src="https://opencollective.com/socketio/backer/21/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/22/website" target="_blank"><img src="https://opencollective.com/socketio/backer/22/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/23/website" target="_blank"><img src="https://opencollective.com/socketio/backer/23/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/24/website" target="_blank"><img src="https://opencollective.com/socketio/backer/24/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/25/website" target="_blank"><img src="https://opencollective.com/socketio/backer/25/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/26/website" target="_blank"><img src="https://opencollective.com/socketio/backer/26/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/27/website" target="_blank"><img src="https://opencollective.com/socketio/backer/27/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/28/website" target="_blank"><img src="https://opencollective.com/socketio/backer/28/avatar.svg"></a>
<a href="https://opencollective.com/socketio/backer/29/website" target="_blank"><img src="https://opencollective.com/socketio/backer/29/avatar.svg"></a>


## Sponsors

Become a sponsor and get your logo on our README on Github with a link to your site. [[Become a sponsor](https://opencollective.com/socketio#sponsor)]

<a href="https://opencollective.com/socketio/sponsor/0/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/1/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/2/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/3/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/4/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/5/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/6/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/7/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/8/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/9/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/9/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/10/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/10/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/11/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/11/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/12/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/12/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/13/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/13/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/14/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/14/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/15/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/15/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/16/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/16/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/17/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/17/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/18/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/18/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/19/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/19/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/20/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/20/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/21/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/21/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/22/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/22/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/23/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/23/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/24/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/24/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/25/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/25/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/26/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/26/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/27/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/27/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/28/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/28/avatar.svg"></a>
<a href="https://opencollective.com/socketio/sponsor/29/website" target="_blank"><img src="https://opencollective.com/socketio/sponsor/29/avatar.svg"></a>


## License

[MIT](LICENSE)





<!--
  -- This file is auto-generated from README_js.md. Changes should be made there.
  -->

# uuid [![Build Status](https://secure.travis-ci.org/kelektiv/node-uuid.svg?branch=master)](http://travis-ci.org/kelektiv/node-uuid) #

Simple, fast generation of [RFC4122](http://www.ietf.org/rfc/rfc4122.txt) UUIDS.

Features:

* Support for version 1, 3, 4 and 5 UUIDs
* Cross-platform
* Uses cryptographically-strong random number APIs (when available)
* Zero-dependency, small footprint (... but not [this small](https://gist.github.com/982883))

[**Deprecation warning**: The use of `require('uuid')` is deprecated and will not be
supported after version 3.x of this module.  Instead, use `require('uuid/[v1|v3|v4|v5]')` as shown in the examples below.]

## Quickstart - CommonJS (Recommended)

```shell
npm install uuid
```

Then generate your uuid version of choice ...

Version 1 (timestamp):

```javascript
const uuidv1 = require('uuid/v1');
uuidv1(); // ⇨ '2c5ea4c0-4067-11e9-8bad-9b1deb4d3b7d'

```

Version 3 (namespace):

```javascript
const uuidv3 = require('uuid/v3');

// ... using predefined DNS namespace (for domain names)
uuidv3('hello.example.com', uuidv3.DNS); // ⇨ '9125a8dc-52ee-365b-a5aa-81b0b3681cf6'

// ... using predefined URL namespace (for, well, URLs)
uuidv3('http://example.com/hello', uuidv3.URL); // ⇨ 'c6235813-3ba4-3801-ae84-e0a6ebb7d138'

// ... using a custom namespace
//
// Note: Custom namespaces should be a UUID string specific to your application!
// E.g. the one here was generated using this modules `uuid` CLI.
const MY_NAMESPACE = '1b671a64-40d5-491e-99b0-da01ff1f3341';
uuidv3('Hello, World!', MY_NAMESPACE); // ⇨ 'e8b5a51d-11c8-3310-a6ab-367563f20686'

```

Version 4 (random):

```javascript
const uuidv4 = require('uuid/v4');
uuidv4(); // ⇨ '1b9d6bcd-bbfd-4b2d-9b5d-ab8dfbbd4bed'

```

Version 5 (namespace):

```javascript
const uuidv5 = require('uuid/v5');

// ... using predefined DNS namespace (for domain names)
uuidv5('hello.example.com', uuidv5.DNS); // ⇨ 'fdda765f-fc57-5604-a269-52a7df8164ec'

// ... using predefined URL namespace (for, well, URLs)
uuidv5('http://example.com/hello', uuidv5.URL); // ⇨ '3bbcee75-cecc-5b56-8031-b6641c1ed1f1'

// ... using a custom namespace
//
// Note: Custom namespaces should be a UUID string specific to your application!
// E.g. the one here was generated using this modules `uuid` CLI.
const MY_NAMESPACE = '1b671a64-40d5-491e-99b0-da01ff1f3341';
uuidv5('Hello, World!', MY_NAMESPACE); // ⇨ '630eb68f-e0fa-5ecc-887a-7c7a62614681'

```

## API

### Version 1

```javascript
const uuidv1 = require('uuid/v1');

// Incantations
uuidv1();
uuidv1(options);
uuidv1(options, buffer, offset);
```

Generate and return a RFC4122 v1 (timestamp-based) UUID.

* `options` - (Object) Optional uuid state to apply. Properties may include:

  * `node` - (Array) Node id as Array of 6 bytes (per 4.1.6). Default: Randomly generated ID.  See note 1.
  * `clockseq` - (Number between 0 - 0x3fff) RFC clock sequence.  Default: An internally maintained clockseq is used.
  * `msecs` - (Number) Time in milliseconds since unix Epoch.  Default: The current time is used.
  * `nsecs` - (Number between 0-9999) additional time, in 100-nanosecond units. Ignored if `msecs` is unspecified. Default: internal uuid counter is used, as per 4.2.1.2.

* `buffer` - (Array | Buffer) Array or buffer where UUID bytes are to be written.
* `offset` - (Number) Starting index in `buffer` at which to begin writing.

Returns `buffer`, if specified, otherwise the string form of the UUID

Note: The default [node id](https://tools.ietf.org/html/rfc4122#section-4.1.6) (the last 12 digits in the UUID) is generated once, randomly, on process startup, and then remains unchanged for the duration of the process.

Example: Generate string UUID with fully-specified options

```javascript
const v1options = {
  node: [0x01, 0x23, 0x45, 0x67, 0x89, 0xab],
  clockseq: 0x1234,
  msecs: new Date('2011-11-01').getTime(),
  nsecs: 5678
};
uuidv1(v1options); // ⇨ '710b962e-041c-11e1-9234-0123456789ab'

```

Example: In-place generation of two binary IDs

```javascript
// Generate two ids in an array
const arr = new Array();
uuidv1(null, arr, 0);  // ⇨ 
  // [
  //    44,  94, 164, 192,  64, 103,
  //    17, 233, 146,  52, 155,  29,
  //   235,  77,  59, 125
  // ]
uuidv1(null, arr, 16); // ⇨ 
  // [
  //    44, 94, 164, 192,  64, 103, 17, 233,
  //   146, 52, 155,  29, 235,  77, 59, 125,
  //    44, 94, 164, 193,  64, 103, 17, 233,
  //   146, 52, 155,  29, 235,  77, 59, 125
  // ]

```

### Version 3

```javascript
const uuidv3 = require('uuid/v3');

// Incantations
uuidv3(name, namespace);
uuidv3(name, namespace, buffer);
uuidv3(name, namespace, buffer, offset);
```

Generate and return a RFC4122 v3 UUID.

* `name` - (String | Array[]) "name" to create UUID with
* `namespace` - (String | Array[]) "namespace" UUID either as a String or Array[16] of byte values
* `buffer` - (Array | Buffer) Array or buffer where UUID bytes are to be written.
* `offset` - (Number) Starting index in `buffer` at which to begin writing. Default = 0

Returns `buffer`, if specified, otherwise the string form of the UUID

Example:

```javascript
uuidv3('hello world', MY_NAMESPACE);  // ⇨ '042ffd34-d989-321c-ad06-f60826172424'

```

### Version 4

```javascript
const uuidv4 = require('uuid/v4')

// Incantations
uuidv4();
uuidv4(options);
uuidv4(options, buffer, offset);
```

Generate and return a RFC4122 v4 UUID.

* `options` - (Object) Optional uuid state to apply. Properties may include:
  * `random` - (Number[16]) Array of 16 numbers (0-255) to use in place of randomly generated values
  * `rng` - (Function) Random # generator function that returns an Array[16] of byte values (0-255)
* `buffer` - (Array | Buffer) Array or buffer where UUID bytes are to be written.
* `offset` - (Number) Starting index in `buffer` at which to begin writing.

Returns `buffer`, if specified, otherwise the string form of the UUID

Example: Generate string UUID with predefined `random` values

```javascript
const v4options = {
  random: [
    0x10, 0x91, 0x56, 0xbe, 0xc4, 0xfb, 0xc1, 0xea,
    0x71, 0xb4, 0xef, 0xe1, 0x67, 0x1c, 0x58, 0x36
  ]
};
uuidv4(v4options); // ⇨ '109156be-c4fb-41ea-b1b4-efe1671c5836'

```

Example: Generate two IDs in a single buffer

```javascript
const buffer = new Array();
uuidv4(null, buffer, 0);  // ⇨ 
  // [
  //   155, 29, 235,  77,  59,
  //   125, 75, 173, 155, 221,
  //    43, 13, 123,  61, 203,
  //   109
  // ]
uuidv4(null, buffer, 16); // ⇨ 
  // [
  //   155,  29, 235,  77,  59, 125,  75, 173,
  //   155, 221,  43,  13, 123,  61, 203, 109,
  //    27, 157, 107, 205, 187, 253,  75,  45,
  //   155,  93, 171, 141, 251, 189,  75, 237
  // ]

```

### Version 5

```javascript
const uuidv5 = require('uuid/v5');

// Incantations
uuidv5(name, namespace);
uuidv5(name, namespace, buffer);
uuidv5(name, namespace, buffer, offset);
```

Generate and return a RFC4122 v5 UUID.

* `name` - (String | Array[]) "name" to create UUID with
* `namespace` - (String | Array[]) "namespace" UUID either as a String or Array[16] of byte values
* `buffer` - (Array | Buffer) Array or buffer where UUID bytes are to be written.
* `offset` - (Number) Starting index in `buffer` at which to begin writing. Default = 0

Returns `buffer`, if specified, otherwise the string form of the UUID

Example:

```javascript
uuidv5('hello world', MY_NAMESPACE);  // ⇨ '9f282611-e0fd-5650-8953-89c8e342da0b'

```

## Command Line

UUIDs can be generated from the command line with the `uuid` command.

```shell
$ uuid
ddeb27fb-d9a0-4624-be4d-4615062daed4

$ uuid v1
02d37060-d446-11e7-a9fa-7bdae751ebe1
```

Type `uuid --help` for usage details

## Testing

```shell
npm test
```

----
Markdown generated from [README_js.md](README_js.md) by [![RunMD Logo](http://i.imgur.com/h0FVyzU.png)](https://github.com/broofa/runmd)
