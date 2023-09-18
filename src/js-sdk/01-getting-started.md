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
const myKeys = new Keys()
const authenticator = new DirectPrivateKeyAuthenticator(myKeys.privateKey)
const bitcoinUtil = {
        walletSyncTimeGap: 3, 
        toDescriptor: miniScriptToDescriptor,
        createWallet: (descriptor) => {
          return new Wallet(
            descriptor,
            'https://mempool.space/testnet/api',
            'testnet',
             15
          )
        },
        canFinalizePsbt: (psbts) => canFinalizePsbt(psbts),
        getTrxId: (trx) => getTrxIdWasm(trx),
        getFee: (psbt) => getFeeWasm(psbt),
        getPsbtUtxos: (psbt) => getPsbtUtxos(psbt),
        toMiniscript: (descriptor) => descriptorToMiniscript(descriptor)
}
const nostrClient = new NostrClient(['wss://test.relay.report'])
const smartVaults = new SmartVaults ({authenticator, bitcoinUtil, nostrClient})
```
