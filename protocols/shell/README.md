# shell

The `shell` protocol provides an interactive command-line interface to the node over a raw byte stream. Sessions run as the caller's identity by default; the `as` argument allows impersonation gated by the `mod.auth.sudo_action` authorization check.

`shell.shell` opens an interactive session. `shell.spec` streams `routing.op_spec` objects describing the ops registered under the shell module.
