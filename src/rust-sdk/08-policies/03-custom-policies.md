# Custom policies

If you need to save more complex policies that are not included in [templates](./02-templates.md), you can use the `save_policy` method:

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let public_keys = vec![...]; // Nostr public keys of users involved in the policy
client
    .save_policy(
        "My custom policy", // Name of the policy
        "Custom policy", // Description
        "...", // Miniscript policy or already compiled descriptor
        public_keys,
    )
    .await?;
# }
```