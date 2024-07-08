# WebSocket close codes

| Close code (uint16) | IANA meaning               | Reserved  | Custom          | Usage |
|---------------------|----------------------------|-----------|-----------------|-------------|
| `0` - `999`         |                            |           | No              | Unused |
| `1000`              | Normal Closure             |           |                 | Successful operation, connection not required anymore |
| `1001`              | Going Away                 |           |                 | Browser tab closing, graceful server shutdown |
| `1002`              | Protocol error             |           |                 | Endpoint received malformed frame |
| `1003`              | Unsupported Data           |           |                 | Endpoint received unsupported frame (e.g. binary-only got text frame, ping/pong frames not handled properly) |
| `1004`              |                            |           | No              | Unused |
| `1005`              | No Status Rcvd             | Yes       |                 | Got no close status but transport layer finished normally (e.g. TCP FIN but no previous CLOSE frame) |
| `1006`              | Abnormal Closure           | Yes       |                 | Transport layer broke (e.g. couldn't connect, TCP RST) |
| `1007`              | Invalid frame payload data |           |                 | Data in endpoint's frame is not consistent (e.g. malformed UTF-8) |
| `1008`              | Policy Violation           |           |                 | Generic code not applicable to any other (e.g. isn't `1003` nor `1009`) |
| `1009`              | Message Too Big            |           |                 | Endpoint won't process large message |
| `1010`              | Mandatory Ext.             |           |                 | Client wanted extension(s) that server did not negotiate |
| `1011`              | Internal Error             |           |                 | Unexpected server problem while operating |
| `1012`              | Service Restart            |           |                 | Server/service is restarting |
| `1013`              | Try Again Later            |           |                 | Temporary server condition forced blocking client's application-based request |
| `1014`              | *Bad gateway*              |           |                 | Server acting as gateway/proxy got invalid response. Equivalent to HTTP `502` |
| `1015`              | TLS handshake              | Yes       |                 | Transport layer broke because TLS handshake failed |
| `1016` - `2999`     |                            | -         | Extensions only | Unused. Extensions or future spec can define them |
| `3000` - `3999`     |                            | Undefined | Yes             | Available for applications, registered first come first serve at IANA |
| `3000`              | Unauthorized               | Undefined | Yes             | Endpoint must be authorized to perform application-based request. Equivalent to HTTP `401` |
| `3003`              | Forbidden                  | Undefined | Yes             | Endpoint is authorized but has no permissions to perform application-based request. Equivalent to HTTP `403` |
| `3008`              | Timeout                    | Undefined | Yes             | Endpoint took too long to respond to application-based request. Equivalent to HTTP `408` |
| `4000` - `4999`     |                            | Undefined | Yes             | Available for applications |

- **Reserved** means WebSocket implementation *reports* it to application, but per spec cannot be *used* as actual close code

- **Custom** means undefined by spec. Application logic and/or WebSocket implementations are allowed to use it however they like, provided common sense that both endpoints will understand them

- **Transport layer** is the protocol via which WebSocket messages get sent. Usually **TCP** or [QUIC](https://datatracker.ietf.org/doc/html/rfc9220) when over HTTP/3

- **Extensions** are spec that changes how messages are sent. They aren't defined by WebSocket spec, implementations don't have to support them, and per RFC must have their details publicly available. One well used example is [`permessage-deflate`](https://datatracker.ietf.org/doc/html/rfc7692)

Relevant links:

- WebSocket spec: https://datatracker.ietf.org/doc/html/rfc6455#section-7.4

- Code registry: https://www.iana.org/assignments/websocket/websocket.xhtml#close-code-number
