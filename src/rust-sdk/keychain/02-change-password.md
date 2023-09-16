# Change password

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

client.change_password(
    || Ok(String::from("current-password")), // Current password
    || Ok(String::from("new-password")), // New password
    || Ok(String::from("new-password")), // Confirmation of new password
)?;
# }
```