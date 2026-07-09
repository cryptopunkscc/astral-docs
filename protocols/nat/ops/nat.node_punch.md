# nat.node_punch

Run the passive (participant) side of a NAT hole-punch with the calling peer. The operation punches a hole with the caller identity itself, so it takes no target argument. Over the channel it receives the caller's `nat.punch_signal` of type `offer`, replies `answer`, receives `ready`, replies `go`, performs the simultaneous UDP punch, then receives and echoes the final `result` signal. On success the resulting hole is registered locally and no further object is returned. The operation fails if the node has no suitable public IPv4 address, or if any signal is out of order, carries a mismatched session, or the punch does not complete.

## Arguments

This operation takes no arguments beyond the implicit input and output format hints.

## Returned objects

The operation exchanges `nat.punch_signal` control messages with the caller over the channel. It returns no object on success; it returns an `error_message` object if a signal is unexpected or the punch fails.

## Examples

```shellsession
$ astral-query nat.node_punch -out json
```
