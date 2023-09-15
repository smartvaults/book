# Constructors

Let's start by constructing the `SmartVaults` struct.

There are 3 possible constructors: `generate`, `restore` and `open`.
All these when constructed return a ready to use client.

## Generate

This constructor generate a random [BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) mnemonic and store
it in a local [encrypted keychain](./keychain.md).

```rust,no_run
use smartvaults_sdk::prelude::*;

let client = SmartVaults::generate(
    "./your-base-path", // A local path where to store all the data
    "account-name", // This will be used for the keychain file name
    || Ok(String::from("password")), // Keychain encryption password
    || Ok(String::from("password")), // Confirmation of the above password
    WordCount::W24, // Number of mnemonic words (possible values are: 12, 18 or 24)
    || Ok(None), // Optional passphrase that will be stored in the keychain
    Network::Testnet, // The bitcoin network to use
)
.await
.unwrap();
```

## Restore

This constructor restore a [BIP39](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) mnemonic and store
it in a local [encrypted keychain](./keychain.md).

```rust,no_run
use smartvaults_sdk::prelude::*;

let client = SmartVaults::restore(
    "./your-base-path", // A local path where to store all the data
    "account-name", // This will be used for the keychain file name
    || Ok(String::from("password")), // Keychain encryption password
    || Ok(String::from("password")), // Confirmation of the above password
    || Ok(Mnemonic::from_str("your menmonic").unwrap()), // A BIP39 mnemonic
    || Ok(Some(String::from("my-optional-passphrase"))), // Optional passphrase that will be stored in the keychain
    Network::Testnet, // The bitcoin network to use
)
.await
.unwrap();
```

## Open

This constructor open an **already existing** keychain.

```rust,no_run
use smartvaults_sdk::prelude::*;

let client = SmartVaults::open(
    "./your-base-path",
    "account-name",
    || Ok(String::from("password")),
    Network::Testnet,
)
.await
.unwrap();
```