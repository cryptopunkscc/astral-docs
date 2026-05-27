# auth.index

Add a stored `mod.auth.signed_contract` to the local auth index. The
referenced object is loaded from the `objects` module, both signatures are
verified, and the contract is stored so it can be consulted by future
authorization decisions. Indexing is idempotent — re-indexing the same
contract is a no-op.

## Arguments

* id (object_id.sha256, required) – Object ID of the `mod.auth.signed_contract` to index.
* in (string) – Optional input stream format (e.g. `json`).
* out (string) – Optional output stream format (e.g. `json`).

## Returned objects

The operation returns one of:
* An `error_message` object if the object cannot be loaded, is not a
  `mod.auth.signed_contract`, or either signature fails to verify.
* An `ack` object once the contract has been indexed (or was already
  present).

## Examples

```shellsession
$ astral-query auth.index -id 9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08 -out json
{"Type":"ack","Object":{}}
```
