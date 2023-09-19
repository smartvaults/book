# Signers

This guide walks you through the process of fetching your owned signers and sharing them with your contacts.

## Table of Contents

1. **Fetching Owned Signers**
2. **Sharing an Owned Signer with a Contact**

------

### Fetching Owned Signers

To get the list of signers that you own, you can use the `getOwnedSigners` method.

```javascript
const mySigners = await smartVaults.getOwnedSigners();
const mySigner = mySigners[0]; // For this example, we are assuming that you have at least one signer
```

------

### Sharing an Owned Signer with a Contact

To share a signer with a contact, use the `saveSharedSigner` method. The method takes two parameters: the `ownedSigner` you wish to share and the public keys of the contacts (`pubKeys`).

```javascript
const pubKeys = [contactPubKey]; // Replace with the actual public keys of the contacts you wish to share the signer with
const sharedSigners = await smartVaults.saveSharedSigner(mySigner, pubKeys);
```
