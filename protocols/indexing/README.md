# indexing

The `indexing` protocol delivers repository change events to registered indexers. An indexer registers with `indexing.register_indexer` to receive a `nonce64` handle, then calls `indexing.subscribe` to receive a stream of `indexing.index` and `indexing.unindex` messages, acknowledging each with an `indexing.ack` before the next change is delivered.

Indexers persist their position per repository as a `Version` counter. The server tracks each indexer's confirmed state and retries unacknowledged changes with exponential back-off. `indexing.remove_index` deregisters an indexer and discards its state.
