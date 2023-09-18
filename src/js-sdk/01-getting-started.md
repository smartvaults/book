# Getting started

## Install dependencies

```shell
npm install @smontero/smartvaults-js-client @smontero/smartvaults-wasm @smontero/nostr-ual --save
```

## Import modules

```javascript
import { NostrClient, SmartVaults, Contact, Keys } from '@smontero/smartvaults-js-client';
import { DirectPrivateKeyAuthenticator } from '@smontero/nostr-ual'
import {
  Wallet,
  miniscript_to_descriptor as miniScriptToDescriptor,
  can_finalize_psbt as canFinalizePsbt,
  get_trx_id as getTrxIdWasm,
  get_fee as getFeeWasm,
  MiniscriptBuilder,
  get_psbt_utxos as getPsbtUtxos,
  descriptor_to_miniscript as descriptorToMiniscript
} from '@smontero/smartvaults-wasm'
```

## Initializing `SmartVaults`

### Parameters for Initialization

1. `authenticator`: An instance of an Authenticator
2. `bitcoinUtil`: Utility functions related to Bitcoin transactions
3. `nostrClient`: An instance of NostrClient for interacting with Nostr relays

```javascript
// Define the authenticator
const myKeys = new Keys()
const authenticator = new DirectPrivateKeyAuthenticator(myKeys.privateKey)

// Define the bitcoin utility functions
const ENDPONIT = 'https://mempool.space/testnet/api'
const NETWORK = 'testnet'
const STOP_GAP = 20 // Stop searching addreses for transactions after this number of consecutive addresses with no transactions is found
const bitcoinUtil = {
        walletSyncTimeGap: 3, // Minutes that have to pass after the last sync, to require another sync when performing an operation
        toDescriptor: miniScriptToDescriptor,
        createWallet: (descriptor) => {
          return new Wallet(
            descriptor,
            ENDPONIT,
            NETWORK,
            STOP_GAP
          )
        },
        canFinalizePsbt: (psbts) => canFinalizePsbt(psbts),
        getTrxId: (trx) => getTrxIdWasm(trx),
        getFee: (psbt) => getFeeWasm(psbt),
        getPsbtUtxos: (psbt) => getPsbtUtxos(psbt),
        toMiniscript: (descriptor) => descriptorToMiniscript(descriptor)
}

// Define the Nostr client
const nostrClient = new NostrClient(['wss://test.relay.report'])

// Initialize SmartVaults
const smartVaults = new SmartVaults ({authenticator, bitcoinUtil, nostrClient})
```
