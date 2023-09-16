# Wipe

Delete the `keychain`

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Delete the keychain
client.wipe("your-password")?;
# }
```