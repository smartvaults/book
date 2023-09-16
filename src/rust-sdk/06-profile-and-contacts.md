# Profile & Contacts

## Profile

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Get your profile (public key and metadata)
let profile: User = client.get_profile().await?;
println!("My public key: {}", profile.public_key());
println!("My name: {}", profile.name());
println!("My metadata: {:#?}", profile.metadata());

// Edit metadata
let metadata = profile.metadata().name("myname").display_name("My Name").nip05("myname@example.com");
client.set_metadata(metadata).await?;
# }
```

## Add/Remove contacts

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Public key from hex
let public_key = XOnlyPublicKey::from_str("ea527e059759d368a55253270454e58e9d6e4fe2e98d302d6e01821fa973259d")?;
// Public key from bech32
let public_key = XOnlyPublicKey::from_bech32("npub1aff8upvht8fk3f2j2vnsg48936wkunlzaxxnqttwqxppl2tnykwsahwngp")?;

// Add a contact
// This method will automatically request metadata of the contact
client.add_contact(public_key).await?;

// Remove a contact
let another_public_key: XOnlyPublicKey = ...;
client.remove_contact(another_public_key).await?;

// Get contact list
let list: Vec<User> = client.get_contacts().await?;
# }
```

## Get metadata of a generic public key


```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let public_key: XOnlyPublicKey = ...;
// This method check if metadata for a public key exists in local database.
// If not exists, will return an empty `Metadata` struct and will request it to relays.
let metadata: Metadata = client.get_public_key_metadata(public_key).await?;
# }
```