# services

The `services` protocol manages discovery and synchronisation of named service advertisements across nodes. Each advertisement is represented as a `services.update` object that records whether a named service is available and which identity provides it.

`services.discover` streams `services.update` objects visible to the caller; in follow mode the channel stays open for live updates. `services.sync` fetches advertisements from a remote identity and stores them in the local registry.
