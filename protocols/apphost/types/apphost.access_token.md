# apphost.access_token

A structure containing an access token issued by the host for a guest
identity.

## Fields

* Identity (identity) – The identity the token authenticates.
* Token (string8) – The token value used in `AuthTokenMsg`.
* ExpiresAt (time) – The instant at which the token expires.

## Example

```json
{
  "Type": "apphost.access_token",
  "Object": {
    "Identity": "0282fee8775757cdd8fda8b220195f5b8611312cd145c5a1a3aa55df210e779b2c",
    "Token": "k7m2q5x9r3v4n8p1",
    "ExpiresAt": "2027-05-27T12:00:00+02:00"
  }
}
```
