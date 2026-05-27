# auth

The `auth` protocol manages capability grants between identities. An issuer
grants a subject a set of `mod.auth.permit`s in a `mod.auth.contract`,
co-signed by both parties as a `mod.auth.signed_contract`. The node indexes
such contracts and consults them, alongside locally registered handlers,
when authorizing typed actions (`mod.auth.action` and its concrete subtypes).

Two operations are exposed: `auth.sign_contract` co-signs a contract
presented on the stream using private keys held by the node, and `auth.index`
verifies a stored `mod.auth.signed_contract` and adds it to the local index.
