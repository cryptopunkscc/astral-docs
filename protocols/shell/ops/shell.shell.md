# shell.shell

Open an interactive shell session on the node. The connection carries a line-oriented text protocol over the raw byte stream. The `as` argument is gated by the `mod.auth.sudo_action` action: the caller must be authorized to act as the target identity.

## Arguments

* as (string8) – Identity to run the session as, given as a hex public key or alias. Defaults to the caller's identity.

## Returned objects

The op accepts the query as a raw byte stream. The session runs until the connection closes or EOF is reached. No typed objects are exchanged; all interaction is line-oriented text over the raw connection.

## Examples

```shellsession
$ astral-query shell.shell
> help
```
