# Connect

In this section we'll see how to connect to a Web App using the [NIP46](https://github.com/nostr-protocol/nips/blob/master/46.md) (Nostr Connect).

## Initialize a new session

To initialize a new session, you'll need a nostr connect URI (it's provided from the app you want connect to).

```rust,no_run
use std::str::FromStr;

# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Parse URI
let uri = NostrConnectURI::forom_str("nostrconnect://f0d056e4bc98d52d53df73fd2f3dac287b1f5f2d868414172759d663987a95e3?metadata=%7B%22name%22%3A%22Smart%20Vaults%22%2C%22description%22%3A%22Bitcoin%20multi-custody%20signature%20orchestration%22%2C%22url%22%3A%22https%3A%2F%2Fsmartvaults.app%22%2C%22icons%22%3A%5B%22https%3A%2F%2Fsmartvaults.app%2Ffavicon.ico%22%5D%7D&relay=wss%3A%2F%2Ftest.relay.report")?;

// Initialize session
client.new_nostr_connect_session(uri).await?;
# }
```

## Get, approve and reject requests

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Get pending requests
let approved: bool = false;
let requests: Vec<NostrConnectRequest> = client.get_nostr_connect_requests(approved).await?;

let first_req: NostrConnectRequest = requests.first().unwrap();
let second_req: NostrConnectRequest = requests.get(1).unwrap();

// Approve a request
client.approve_nostr_connect_request(first_req.event_id).await?;

// Reject a request
client.reject_nostr_connect_request(second_req.event_id).await?;
# }
```

## Disconnect from a session

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Get current sessions
let sessions: Vec<(NostrConnectURI, Timestamp)> = client.get_nostr_connect_sessions().await?;

// Disconnect from all sessions
for (uri, _timestamp) in sessions.into_iter() {
    // Disconnect session from app public key
    client.disconnect_nostr_connect_session(uri.public_key).await?;
}
# }
```