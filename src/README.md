Smart Vaults is an interoperable smart wallet ecosystem for Bitcoin. It defines a specification (with implementations in Javascript and Rust) for managing partially signed bitcoin transactions (PSBTs) and miniscript spending policies over Nostr relays. 

Smart Vaults is intentionally designed to work with limited backend infrastructure; the only requirements are a Bitcoin node and a Nostr relay. This makes it easy for sovereignty seekers to self-host their own and simplifies integration for developers. 

One of the first steps to using Smart Vaults is creating a new signer key. This must be done on the mobile app or desktop GUI. The extended public key (xpub) of this signer is shared with Nostr contacts that you wish to collaborate with. Signers are encrypted and only shared with contacts you approve individually.

Signers are shared via the Nostr public key (npub), which can be done app-to-app via QR code or via copy/paste out of band. There is also an invite process that prompts a user to download the app, create a signer, and then share it with the inviter.

Now that signers have been share among a group, they can begin creating vaults using the signers. 

Currently, the mobile app and desktop apps are the only supported signers. Our initial focus is optimizing for easy and fast hot wallet approvals for vaults. However, users can have multiple signers and we will support hardware wallets in the future.

When a new vault is created, an encryption group is created for the vault participants to share information that only they can view. This includes the vault configuration (spending policy), name, description, spending proposals, and utxo labels.

Proof of Reserve
Smart Vaults supports proof-of-reserve attestations on vaults. These proofs can be generated to cryptographically prove that the members of the vault have key access and ownership over the vault’s set of UTXOs.

Regular proof-of-reserve attestations are an important component of custodial hygiene, especially in multi-party or multi-institutional custody vaults.
