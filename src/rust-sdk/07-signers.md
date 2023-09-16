# Signers

Signers are descriptors that you can share with contacts (or with other users) to simplify the
process of policies creation.


## The SmartVaults signer

The `SmartVaults` signer it's derived from your local seed.
It's use the following derivation path: `m/86'/<coin>'/784923'` (the `coin` depends on the selected `network`)

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Save the SmartVaults signer (if not exists)
client.save_smartvaults_signer().await?;
# }
```

## External signers

You can save external signers (like `AirGap` devices).

```rust,no_run
use std::str::FromStr;

# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let fingerprint = Fingerprint::from_str("7356e457")?;
let descriptor: Descriptor<DescriptorPublicKey> = Descriptor::from_str("[7356e457/86'/1'/784923']tpubDCvLwbJPseNux9EtPbrbA2tgDayzptK4HNkky14Cw6msjHuqyZCE88miedZD86TZUb29Rof3sgtREU4wtzofte7QDSWDiw8ZU6ZYHmAxY9d/0/*")?;
let signer = Signer::airgap("Coldcard", "Description", fingerprint, descriptor)?;
client.save_signer(signer).await?;
# }
```

Note: **only** `taproot` descriptors are supported

## Share a signer

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Get my signers
let signers: Vec<GetSigner> = client.get_signers().await?;

// Get the first signer
let signer_id = signers.first().unwrap().signer_id;

// Public key of the user to share the signer
let public_key: XOnlyPublicKey = ...;

// Share
client.share_signer(signer_id, public_key).await?;
# }
```