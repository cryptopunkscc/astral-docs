# astral-query

The `astral-query` tool can be used to send queries to nodes on the Astral 
Network from the command line.

The syntax is:

`astral-query [target:]<operation> [-<param> <val>] ...`

The target can be the hex string of the target identity or its alias.

A `target:` that names another node needs the [`Network` zone](../core-definitions/zone.md),
which only an authenticated caller has. Export an access token first:

`export ASTRALD_APPHOST_TOKEN=<token>`

Without it the call is anonymous, the `Network` zone is stripped, and the query
fails locally with `route_not_found` before reaching the target — exporting the
token, not changing the query, is the fix. A token issued to a
[`User`](../core-definitions/user.md) also routes the query as that user, which
the target may require in order to accept it.