# Configs & Relays

Once the client is constructed, you can start editing the default configs and relays.

Note: both the configs and relays are persistent, so you **not** need to edit them every time.

## View and edit configs

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Get the current configs
let config = client.config();

// View the current configs
println!("Current electrum endpoint: {}", config.electrum_endpoint().await?);
println!("Current proxy: {}", config.proxy().await.ok());
println!("Current block explorer: {}", config.block_explorer().await?);

// Edit the electrum endpoint
config.set_electrum_endpoint(Some("tcp://127.0.0.1:50001")).await;

// Edit the block explorer url
let url = Url::parse("http://myblockexplorer.local")?;
config.set_block_explorer(Some(url)).await;

// Save the configs in the persistent file
config.save().await?;
# }
```

## View relays

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

for (relay_url, relay) in client.relays().await.into_iter() {
    let stats = relay.stats();
    println!("Url: {relay_url}");
    println!("Status: {}", relay.status().await);
    println!("Attempts: {}", stats.attempts());
    println!("Success: {}", stats.success());
    println!("Bytes sent: {}", stats.bytes_sent());
    println!("Bytes received: {}", stats.bytes_received());
    if let Some(latency) = stats.latency().await {
        println!("Latency: {} ms", latency.as_millis());
    }
}
# }
```

## Edit relays

```rust,no_run
use std::net::{Ipv4Addr, SocketAddr, SocketAddrV4};
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

// Add a relay (without proxy)
client.add_relay("wss://you.relay.com", None).await?;

// Add a relay (with proxy)
let proxy = Some(SocketAddr::V4(SocketAddrV4::new(Ipv4Addr::LOCALHOST, 9050)));
client.add_relay("wss://you.relay2.com", Some(proxy)).await?;

// Remove a relay
client.remove_relay("wss://you.relay.com").await?;
# }
```