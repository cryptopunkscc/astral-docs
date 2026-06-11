# kcp

The `kcp` protocol provides KCP-over-UDP transport for the astral network. It dials and accepts connections using `mod.kcp.endpoint` objects, each identifying a remote host by IP address and UDP port.

The module supports ephemeral listeners and per-endpoint local port mappings. Ephemeral listeners are created and destroyed with `kcp.new_ephemeral_listener` and `kcp.close_ephemeral_listener`. Local port mappings that route a remote endpoint to a specific local UDP port are managed with `kcp.set_endpoint_local_port`, `kcp.remove_endpoint_local_port`, and `kcp.list_endpoint_local_mappings`, which streams `mod.kcp.endpoint_local_mapping` objects.
