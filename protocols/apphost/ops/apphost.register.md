# apphost.register

Provision a fresh guest identity end-to-end: generate a new keypair, sign and
store an app contract between the new identity and the node, and issue an
access token. Used by apps/agents to bootstrap themselves on first run.

## Arguments

This operation takes no arguments.

## Returned objects

The operation returns one of:
* An `error_message` object if any step failed.
* An `apphost.access_token` object containing the new guest's token.

## Examples

```shellsession
$ astral-query apphost.register -out json
{"Type":"apphost.access_token","Object":{"Identity":"03864ef025fde8fb587d989186ce6a4a186895ee44a926bfc370e2c366597a3f8f","Token":"b9c2e1a3d4f5867a","ExpiresAt":"2036-05-25T12:00:00+02:00"}}
```
