# WebSocket close codes

| Close code (uint16) | Codename                          | Internal | Customizable | Description                                                                                   |
|---------------------|-----------------------------------|----------|--------------|-----------------------------------------------------------------------------------------------|
| 0-999               | -                                 | Yes      | No           | Unused                                                                                        |
| 1000                | `CLOSE_NORMAL`                    | No       | No           | Successful operation, regular socket shutdown                                                 |
| 1001                | `CLOSE_GOING_AWAY`                | No       | No           | One of the socket endpoints is exiting                                                        |
| 1002                | `CLOSE_PROTOCOL_ERROR`            | No       | No           | Error in one of the endpoints while processing a known message type                           |
| 1003                | `CLOSE_UNSUPPORTED`               | No       | No           | Endpoint received unsupported data type (text/binary)                                         |
| 1004                | -                                 | Yes      | No           | Unused                                                                                        |
| 1005                | `CLOSED_NO_STATUS`                | Yes      | No           | Expected close status, received none                                                          |
| 1006                | `CLOSE_ABNORMAL`                  | Yes      | No           | No close code frame has been receieved                                                        |
| 1007                | *Unsupported Data*                | No       | No           | Endpoint received inconsistent message (e.g. non-UTF8 data within a string)                   |
| 1008                | *Policy Violation*                | No       | No           | Endpoint policy was violated, is a generic code used when codes 1003 and 1009 aren't suitable |
| 1009                | `CLOSE_TOO_LARGE`                 | No       | No           | Data frame size is too large                                                                  |
| 1010                | *Missing Extension*               | No       | No           | Client asked for extension that server didn't reply with                                      |
| 1011                | *Internal Error*                  | No       | No           | Internal server error while operating                                                         |
| 1012                | *Service Restart*                 | No       | No           | Server/service is restarting                                                                  |
| 1013                | *Server Overload/Try Again Later* | No       | No           | Try Again Later code; temporary server condition forced to block client's request             |
| 1014                | -                                 | Yes      | No           | Unused; reserved for later                                                                    |
| 1015                | *TLS Handshake Fail*              | Yes      | No           | TLS handshake failure                                                                         |
| 1016-1999           | -                                 | Yes      | No           | Reserved for later                                                                            |
| 2000-2999           | -                                 | Yes      | No           | Reserved for websocket extensions                                                             |
| 3000-3999           | -                                 | Yes      | Yes          | Reserved for frameworks, can be registered at IANA                                            |
| 4000-4999           | -                                 | No       | Yes          | Available for applications                                                                    |
