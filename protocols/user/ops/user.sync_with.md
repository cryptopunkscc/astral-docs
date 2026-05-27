# user.sync_with

Trigger this node to pull the asset list from a specific sibling node by
calling `user.sync_assets` against it. Used to force a one-shot reconciliation
without waiting for a sibling notification.

## Arguments

* node (identity, required) – Identity of the sibling node to sync with.
* start (uint64, optional) – Height to start syncing from. Defaults to `0`.

## Returned objects

The operation returns one of:
* An `ack` once the sync completes.
* An `error_message` if the remote sync failed.

## Examples

```shellsession
$ astral-query user.sync_with -node 0282fee8...779b2c -out text
#[ack]
```
