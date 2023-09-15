# Funding

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Get first policy
let policy = client.get_policies().await?.first().unwrap();

// OR

// Get a specific policy by ID
let policy = client.get_policy_by_id(policy_id).await?;

// Get a new address
let GetAddress { address, .. } = client.get_address(policy.policy_id, AddressIndex::New).await?;
println!("Address: {}", address.assume_checked());
# }
```