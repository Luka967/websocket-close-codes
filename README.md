# WebSocket close codes

| Close code (uint16) | Codename                          | Internal | Customizable | Description |
|---------------------|-----------------------------------|----------|--------------|-------------|
| 0 - 999               | -                                 | Yes      | No           | Unused |
| 1000                | `CLOSE_NORMAL`                    | No       | No           | Successful operation / regular socket shutdown |
| 1001                | `CLOSE_GOING_AWAY`                | No       | No           | An endpoint is leaving (browser tab closing) |
| 1002                | `CLOSE_PROTOCOL_ERROR`            | Yes      | No           | Endpoint received a malformed frame |
| 1003                | `CLOSE_UNSUPPORTED`               | Yes      | No           | Endpoint received an unsupported frame |
| 1004                |                                   | Yes      | No           | Reserved |
| 1005                | `CLOSED_NO_STATUS`                | Yes      | No           | Expected close status, received none |
| 1006                | `CLOSE_ABNORMAL`                  | Yes      | No           | No close code frame has been receieved |
| 1007                | *Unsupported Data*                | No       | No           | Endpoint received inconsistent message (e.g. malformed UTF-8) |
| 1008                | *Policy Violation*                | No       | No           | Generic code used for situations other than 1003 and 1009 |
| 1009                | `CLOSE_TOO_LARGE`                 | No       | No           | Endpoint won't process large frame |
| 1010                | *Missing Extension*               | No       | No           | Client wanted an extension which server did not reply with |
| 1011                | *Internal Error*                  | Yes      | No           | Internal server error while operating |
| 1012                | *Service Restart*                 | No       | No           | Server/service is restarting |
| 1013                | *Server Overload/Try Again Later* | No       | No           | Try Again Later code; temporary server condition forced to block client's request |
| 1014                | *Bad Gateway*                     | No       | No           | Server acting as gateway received an invalid response |
| 1015                | *TLS Handshake Fail*              | Yes      | No           | TLS handshake failure |
| 1016 - 1999           |                                   | Yes      | No           | Reserved for later |
| 2000 - 2999           |                                   | Yes      | No           | Reserved for websocket extensions |
| 3000 - 3999           |                                   | Yes      | Yes          | Reserved for frameworks / extensions, can be registered first come first serve at IANA |
| 4000 - 4999           |                                   | No       | Yes          | Available for applications |
