# HTTP Transport

* The `Node` provides HTTP interface for sending `Queries`.
* The default HTTP endpoint for all calls is `http://localhost:8624/`.
* HTTP requests are authenticated using an `Access Token` provided as a bearer 
  token in the HTTP Authorization header.
* The `Query String` is passed as the path in the HTTP request.
* The `Target` of a `Query` is set by adding "X-Astral-Target" request 
  header containing the `Identity` of the target node (pubkey hex string).
* The default `Target` is the local `Node`.
* The request headers should contain "Accept: application/json" and
  "Content-Type: application/json".
* API calls respond with JSON lines containing `Objects` using the
  `JSON Encoding`
* HTTP response headers will contain "X-Astral-Guest-Identity" with the 
  `Identity` authenticated via the `Access Token`.
* HTTP response headers will contain "X-Astral-Host-Identity" with the 
  `Identity` of the hosting `Node`.