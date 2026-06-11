# tcp

The `tcp` protocol provides TCP-based transport for astral node connectivity: dialing outbound connections, accepting inbound connections, and managing ephemeral listeners on dynamic ports.

Endpoints are represented as `mod.tcp.endpoint` objects encoding an IP address and port. The module exposes two ops: `tcp.new_ephemeral_listener` starts a listener on a given port; `tcp.close_ephemeral_listener` stops it.
