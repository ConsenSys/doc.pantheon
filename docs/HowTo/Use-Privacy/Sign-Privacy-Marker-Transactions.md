description: How to sign a Privacy Marker Transaction
<!--- END of page meta data -->

# Signing Private Marker Transactions

Private Marker Transactions can be signed with a random key or private key. To sign Private Marker Transactions with a private key, use [`--privacy-marker-transaction-signing-key-file`](../../Reference/Pantheon-CLI/Pantheon-CLI-Syntax.md#privacy-marker-transaction-signing-key-file) when starting Pantheon.

!!! important
    In networks where gas is paid, a funded private key must be specified.
    
In [free gas networks](../../HowTo/Configure-Pantheon/FreeGas.md), exclude `--privacy-marker-transaction-signing-key-file` to sign the Private Marker Transaction with a random key to add additional anonymity.

!!! note
    During the [private transaction process](../../Concepts/Privacy/Private-Transaction-Processing.md), Private Marker Transactions are signed in Pantheon.