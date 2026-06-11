# ip

The `ip` protocol provides the `mod.ip.ip_address` type, a unified representation of an IPv4 or IPv6 address, and monitors local network interface changes.

The module polls local network interfaces and emits a `mod.ip.events.network_address_changed` event whenever addresses are added or removed. Three query ops expose address information: `ip.local_addrs` streams current interface addresses, `ip.public_ip_candidates` streams addresses considered reachable from the public internet, and `ip.default_gateway` returns the default gateway address.
