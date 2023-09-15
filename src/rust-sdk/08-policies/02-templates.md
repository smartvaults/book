# Templates

This library provide some `templates` to simplify the policies creation. 
Currently the following templates are available:
* Multisig (M of N)
* Social recovery: 1 spending key and N others with a `relative` timelock (funds can be spent after a sequence of N blocks)
* Inheritance: 1 spending key and N others with an `absolute` timelock (funds can be spent after the block or timestamp X)
* Hold: 1 spending key and a `relative` timelock

## Save a template

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let client = ...; // The client that you before constructed

let public_keys = vec![...]; // Nostr public keys of users involved in the policy
let template = ...; // See below examples
client
    .save_policy_from_template(
        "My Policy", // Name of the policy
        "Policy created from a template", // Description
        template,
        public_keys,
    )
    .await?;
# }
```

### Examples

To simplify the code below, I define all the descriptors used here:

```rust,no_run
use std::str::FromStr;
use smartvaults_sdk::core::miniscript::DescriptorPublicKey;

let key1 = DescriptorPublicKey::from_str("[7356e457/86'/1'/784923']tpubDCvLwbJPseNux9EtPbrbA2tgDayzptK4HNkky14Cw6msjHuqyZCE88miedZD86TZUb29Rof3sgtREU4wtzofte7QDSWDiw8ZU6ZYHmAxY9d/0/*").unwrap();
let key2 = DescriptorPublicKey::from_str("[4eb5d5a1/86'/1'/784923']tpubDCLskGdzStPPo1auRQygJUfbmLMwujWr7fmekdUMD7gqSpwEcRso4CfiP5GkRqfXFYkfqTujyvuehb7inymMhBJFdbJqFyHsHVRuwLKCSe9/0/*").unwrap();
let key3 = DescriptorPublicKey::from_str("[f3ab64d8/86'/1'/784923']tpubDCh4uyVDVretfgTNkazUarV9ESTh7DJy8yvMSuWn5PQFbTDEsJwHGSBvTrNF92kw3x5ZLFXw91gN5LYtuSCbr1Vo6mzQmD49sF2vGpReZp2/0/*").unwrap();
```

## Multisig 1 of 2

Using the `key1` and `key2` to create a multisig `1 of 2`

```rust,no_run
# use std::str::FromStr;
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let template = PolicyTemplate::multisig(1, vec![key1, key2]);
# }
```

## Social recovery

Using `key1` as spending key and `key2` and `key3` as recovery keys with a `relative` timelock of `6 blocks`

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let older = Sequence(6); // Relative timelock of 6 blocks
let recovery = RecoveryTemplate::social_recovery(2, vec![key2, key3], older);
let template = PolicyTemplate::recovery(key1, recovery);
# }
```

## Inheritance

Using `key1` as spending key and `key2` and `key3` as recovery with an `absolute` timelock set at block `840000`

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let after = AbsoluteLockTime::from_height(840_000)?; // Absolute timelock (funds can be spent after block 840000)
let recovery = RecoveryTemplate::inheritance(2, vec![key2, key3], after);
let template = PolicyTemplate::recovery(key1, recovery);
# }
```

## Hold

Using a `single key` with a `relative` timelock

```rust,no_run
# use smartvaults_sdk::prelude::*;
#
# #[tokio::main]
# async fn main() {
let older = Sequence(10_000);
let template = PolicyTemplate::hold(key1, older);
# }
```