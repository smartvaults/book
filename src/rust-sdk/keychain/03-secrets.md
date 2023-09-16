# Secrets

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let secp = Secp256k1::new();

let network: Network = client.network();
let keychain: Keychain = client.keychain();
let secrets: Secrets = keychain.secrets(network, &secp)?;

println!("Entropy: {}", secrets.entropy);
println!("Mnemonic: {}", secrets.mnemonic);
if let Some(passphrase) = &secrets.passphrase {
    println!("Passphrase: {}", passphrase);
}
println!("Seed (hex): {}", secrets.seed_hex);
println!("Root Key (BIP32): {}", secrets.root_key);
println!("Fingerprint: {}", secrets.fingerprint);
# }
```