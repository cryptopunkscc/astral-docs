# apphost

The `apphost` protocol exposes on-device APIs that let local apps access the
astral network via the node — access token issuance, query handler
registration, app contract installation, and object holds.

A local app connects as an anonymous guest or authenticates with an access
token. An anonymous (or expired-token) guest is confined to the `Device` and
`Virtual` [`Zones`](../../core-definitions/zone.md) — the `Network` zone is
stripped from its queries, so it cannot reach other nodes (a query to another
node fails with `route_not_found`). Authenticating retains the `Network` zone
and binds the session, and the queries it makes, to the token's
[`Identity`](../../core-definitions/identity.md).
