# utp

The `utp` protocol provides uTP (Micro Transport Protocol) transport for astral node connectivity. uTP layers reliable, congestion-controlled streams over UDP, so each connection is dialed and accepted over a UDP host and port.

Endpoints are represented as `mod.utp.endpoint` objects, each identifying a remote host by IP address and UDP port. The network name of every uTP endpoint is `utp`.
