# Proposals

In this section we'll see how to create a `spending` proposal and how to `approve` and `finalize` it. 

## Spend

Create a new `spending` proposal

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let policy_id: EventId = ...; // Get from policies list or pass a specific event ID

// Create a new proposal
let proposal: Proposal = client
    .spend(
        policy_id,
        Address::from_str("mohjSavDdQYHRYXcS3uS6ttaHP8amyvX78")?, // Dastination address
        Amount::Custom(10_934), // Use `Amount::Max` to send all funds
        "Back to the faucet", // Description
        FeeRate::Priority(Priority::Medium), // Use `FeeRate::Rate(1.0)`` to specify the sat/vByte
        None, // Specify the UTXOs to use (optional)
        None, // Specify the policy path to use (needed only if exists a timelock in the policy descriptor)
        false, // Allow usage of UTXOs frozen by others proposals
    )
    .await?;
println!("New proposal: {proposal:#?}");
# }
```

## Approvals

Currently you can approve a proposal with the `seed` stored in the [keychain](./keychain.md) or use an `AirGap` signer and import
the signed PSBT.

### Approve with the seed

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let proposal_id: EventId = ...; // Id of a proposal
// Ex. let proposal_id: EventId = proposal.proposal_id;

// Approve a proposal with the stored seed
client.approve(proposal_id).await?;
# }
```

### Approve with a signed PSBT (AirGap signer)

```rust,no_run
use std::str::FromStr;
use smartvaults_sdk::core::bitcoin::psbt::PartiallySignedTransaction;

# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let proposal_id: EventId = ...; // Id of a proposal
// Ex. let proposal_id: EventId = proposal.proposal_id;

// Approve a proposal with a PSBT
let signed_psbt = PartiallySignedTransaction::from_str("base64-psbt")?;
client.approve_with_signed_psbt(proposal_id, signed_psbt).await?;
# }
```

## Finalization

When the proposal is signed, you can finalize it.

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let proposal_id: EventId = ...;
let proposal: GetProposal = client.get_proposal_by_id(proposal_id).await?;

// Check if proposal is signed
if proposal.signed {
    // Finalize the proposal and broadcast the TX
    client.finalize(proposal_id).await?;
} else {
    println!("This proposal is not fully signed yet!");
}
# }
```