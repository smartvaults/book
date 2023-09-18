# Creating a Vault

In this example, we will create a 2-of-2 multisig vault, but as you will see, the process is similar for other types of vaults.

### Fetching the Signer's Key

To create a vault we need keys, once you have fetched your signers, get the key for the signer you wish to use.

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

Notice that the only assumption the `savePolicy` methods makes about the miniscript is that it is a valid miniscript. This means that you can use any miniscript you want, the Smart Vaults Web app offers a few templates to make it easier to create common types of vaults, but also allows you to create custom vaults.

------

### Basic Fetching of Vaults

To fetch vaults without any specific pagination, you can simply call the `getPolicies` method without any arguments.

```javascript
const policies = await smartVaults.getPolicies();
```

This will return an array of `PublishedPolicy` objects.

------

### Deleting a Vault

To delete a vault, you can use the `deletePolicy` method.

```javascript
await smartVaults.deletePolicies(policyId);
```

We will explore the vault methods in more detail in the next section.
