# mod.user.expulsion

The unsigned body of a swarm ban: Issuer permanently bans Subject from the swarm. Wrap it in `mod.user.signed_expulsion` before storing, propagating, or verifying.

## Fields

* Issuer (identity) – Identity of the user issuing the ban.
* Subject (identity) – Identity of the node or user being banned.
* ExpelledAt (time) – Timestamp at which the ban was issued.

## Example

```json
{
  "Type": "mod.user.expulsion",
  "Object": {
    "Issuer": "0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c",
    "Subject": "03a7c1f5b9d4e62a8f730ce15d2b4a9c11e8d77c3b5f04a6d92e1b8f72c4d3e5a6",
    "ExpelledAt": "2026-06-19T10:00:00Z"
  }
}
```
