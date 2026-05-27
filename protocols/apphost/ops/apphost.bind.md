# apphost.bind

Bind the lifetime of registered IPC handlers to the query session. The host
acknowledges, then waits for a `mod.apphost.bind_msg` containing the token of
the handlers to bind. When the session closes, all handlers registered with
that token are removed. Local-only — queries from the network are rejected.

## Arguments

This operation takes no arguments.

## Returned objects

The operation streams:
* An `ack` object once the session is bound.
* An `error_message` object if the bind message could not be processed.

The caller must then send a `mod.apphost.bind_msg` over the same channel.

## Examples

```shellsession
$ astral-query apphost.bind -out text
#[ack]
```
