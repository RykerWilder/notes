# HTTP Status

HTTP status are 3-digit numeric codes that a web server sends to the browser (or client) to communicate the outcome of a request.

**Success Codes (2xx)**
| Code   | Name                     | Description                                                                 |
|--------|--------------------------|-----------------------------------------------------------------------------|
| 200    | OK                       | Request completed successfully                                              |
| 201    | Created                  | Request completed and new resource created                                  |
| 204    | No Content               | Request completed but no content to return                                  |

---

**Redirections (3xx)**
| Code  | Name                     | Description                                                                |
|-------|--------------------------|----------------------------------------------------------------------------|
| 301   | Moved Permanently        | The resource has been moved permanently                                    |
| 302   | Found                    | The resource is temporarily elsewhere                                      |
| 304   | Not Modified             | The resource is not modified (used for cache)                              |

---

**Client Errors (4xx)**
| Code   | Name                     | Description                                                                 |
|--------|--------------------------|-----------------------------------------------------------------------------|
| 400    | Bad Request              | The request is malformed or syntactically incorrect                         |
| 401    | Unauthorized             | Missing or invalid authentication                                           |
| 403    | Forbidden                | The client does not have permission to access the resource                  |
| 404    | Not Found                | The requested resource was not found                                        |
| 405    | Method Not Allowed       | HTTP method not supported for this resource                                 |
| 409    | Conflict                 | Conflict with the current state of the server                               |
| 429    | Too many requests        | The client has exceeded the number of requests                              |

---

**Server Errors (5xx)**
| Code   | Name                     | Description                                                                 |
|--------|--------------------------|-----------------------------------------------------------------------------|
| 500    | Internal Server Error    | The request is malformed or syntactically incorrect                         |
| 501    | Not Implemented          | Missing or invalid authentication                                           |
| 502    | Bad Gateway              | The client does not have permission to access the resource                  |
| 503    | Service Unavailable      | The requested resource was not found                                        |
| 504    | Gateway Timeout          | HTTP method not supported for this resource                                 |