telehash secure mesh protocol (v3)
==================================

> this is a draft (issues and pull requests welcome), planning for release version in 02/2015

![logo](../logo/mesh-logo-128.png)

Telehash is a project to create interoperable private mesh networking:

* 100% end-to-end encrypted at all times
* designed to complement and add to existing transport security
* easy to use for developers to encourage wider adoption of privacy
* manages active link state on all connections
* native implementations to each language/platform
* capable of using different transport protocols
* supports bridging and routing privately by default and optionally via a [public DHT](https://github.com/telehash/dotPublic)
* each endpoint has verifiable unique fingerprint
* provides native tunneling of TCP/UDP, HTTP, WebSockets, and more
* strict privacy, no content, identity, or metadata is ever revealed to 3rd parties
* designed for compatibility between embedded device, mobile, and web usage
* supports an automatic discovery mode on local networks when available
* [more background](background.md)

The full protocol is a composite of different individual specifications:

* [hashname](hashname/) - public key fingerprint (address format)
* [lob](lob/) - length-object-binary, json+binary serialization (packetization)
* [e3x](e3x/) - end-to-end encrypted exchange (wire encoding, crypto)
* [mesh](mesh.md) - common channels to establish links to peers and maintain a private mesh
* [uri](uri.md) - how to encode/decode endpoint info via URIs for out-of-band bootstrapping
* [transports](transports/) - details (encoding, timeouts, discovery, etc) for mapping/supporting different network transports
* [logo](../logo/) - for use to represent telehash mesh support in apps 

### Implementations

Each implementation provides a library API adapted to its platform or language but they all strive to offer similar functionality including handling hashnames, URIs, and packets (lob), higher level interfaces to create a mesh and links within it, and lower level tools for e3x, transports/pipes, managing keys, etc.  Refer to the [implementers guide](guides/implementers.md) for an overview of the typical methods and patterns.

Experimental implementations are being actively developed at:

* [telehash-js](https://github.com/telehash/telehash-js)
* [telehash-c](https://github.com/telehash/telehash-c).
* [gogotelehash](https://github.com/telehash/gogotelehash)
* [others in progress](https://github.com/telehash)


|              | hashname | link | uri | routing | streams | sockets | udp | tcp | http | tls | webrtc | bluetooth |
|:------------:|:--------:|:----:|:---:|:-------:|:-------:|:-------:|:---:|:---:|:----:|:---:|:------:|:---------:|
|    node.js   |     ✓    |   ✓  |  ✍ |    ✓    |    ✓    |    ✓    |  ✓  |  ✓  |   ✓  |  ✍ |   ✍   |           |
|  browser js  |     ✓    |  ✍  |     |         |         |         |     |     |  ✍  |     |   ✍   |           |
|   c - unix   |     ✓    |   ✓  |  ✍ |    ✍   |    ✍   |    ✍   |  ✓  |  ✓  |      |     |        |           |
| c - embedded |     ✓    |   ✓  |  ✍ |         |    ✍   |    ✍   |  ✍ |  ✍ |      |     |        |           |
|      go      |     ✓    |   ✓  |     |         |         |         |  ✓  |     |      |     |        |           |
