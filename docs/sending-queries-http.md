# Sending Queries

The `Node` provides HTTP interface for sending queries to the `Astral Network`.
 
All `Queries` are sent to the local node, but this can be changed via
an HTTP header as described below.

## API Endpoint

The default HTTP endpoint for all calls is `http://localhost:8624/`.

All API calls should send an "Accept: application/json" and a "Content-Type: 
application/json" headers.

All API calls respond via JSON lines with objects using the standard container
described in this specification.

## Authentication

The API is authenticated using an access token. The access token can be passed
either as a bearer token using standard HTTP authorization. The `Identity`
assigned to the client will be provided via the 'X-Astral-Guest-Identity' HTTP 
header. The `Identity` of the hosting `Node` will be provided via the 
'X-Astral-Host-Identity' HTTP header.

## Targeting other nodes

The api call can be sent to a specific node by specifying the node
`Identity` (the public key in hex string) in the 'X-Astral-Target' HTTP header.
If no target is specified, the call will be sent to the local node.