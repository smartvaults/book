# Creating a Vault

This guide will show you how to create a 2-of-2 multisig vault in SmartVaults.

## Table of Contents

1. **Fetching the Signer's Key**
2. **Getting the Co-Signer's Key**
3. **Setting the Threshold and Creating Miniscript**
4. **Defining Additional Parameters**
5. **Creating the Vault**

------

### Fetching the Signer's Key

After obtaining your signers, fetch the key for the signer you're interested in.

```javascript
const mySignerKey = mySigner.key;
```

------

### Getting the Co-Signer's Key

Retrieve the key of a co-signer to include in the multisig vault.

```javascript
const coSigner = await smartVaults.getSharedSigners();
const coSignerKey = coSigner[0].key;
```

------

### Setting the Threshold and Creating Miniscript

Create a miniscript that specifies the threshold and keys for the 2-of-2 multisig.

```javascript
const threshold = 2;
const keys = [mySignerKey, coSignerKey];
const miniscript = MiniscriptBuilder.multisig({threshold, keys});
```

------

### Defining Additional Parameters

Define other necessary parameters, like the name and description of the vault, and the public keys of vault participants.

```javascript
const name = 'My First Vault';
const description = "2 of 2 Multisig";
const nostrPublicKeys = [myPublicKey, contactPubKey];
```

------

### Creating the Vault

Finally, create the vault by invoking the `savePolicy` method.

```javascript
await smartVaults.savePolicy({ name, description, miniscript, nostrPublicKeys });
```

### Basic Fetching of Vaults

To fetch vaults without any specific pagination, you can simply call the `getPolicies` method without any arguments.

```javascript
const policies = await smartVaults.getPolicies();
```

This will return an array of `PublishedPolicy` objects.
