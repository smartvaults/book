# Creating Proposals

## Overview

The `spend` method is used to create a spending proposal, first, let's look at the method definition.

## Method Signature

```typescript
spend(payload: SpendProposalPayload): Promise<PublishedSpendingProposal>
```

### Parameters

#### `payload: SpendProposalPayload`

The payload for the spending proposal.

- `policy`: PublishedPolicy object.
- `to_address`: The recipient's address.
- `description`: Description of the proposal.
- `amountDescriptor`: Amount to be spent.
- `feeRatePriority`: Fee rate priority (e.g., 'low', 'medium', 'high').
- `policyPath`: Policy path.
- `utxos`: List of unspent transaction outputs (UTXOs) to be used. (Optional)
- `useFrozenUtxos`: Flag to specify whether frozen UTXOs can be used. (Optional)

### Returns

```typescript
Promise<PublishedSpendingProposal>
```

A Promise that resolves to a `PublishedSpendingProposal` object representing the published spending proposal.

## Errors

The method may throw various errors under certain conditions:

- **Invalid UTXOs**: If the provided UTXOs are invalid.
- **Frozen UTXOs Without Flag**: If frozen UTXOs are provided but `useFrozenUtxos` is not set to `true`.
- **Transaction Building Error**: If an error occurs while building the transaction.
- **Publishing Error**: If an error occurs while publishing the proposal.

## Example Usage

Here's an example code snippet that demonstrates how to use the `spend` method to create a spending proposal:

```javascript
const payload = {
  policy: somePublishedPolicyObject,
  to_address: "abc123",
  description: "A spending proposal",
  amountDescriptor: 10,
  feeRatePriority: 'high',
  policyPath: new Map([['nodeId',[0,1,2]]]) // Optional but needed if the policy descriptor has more than one path,
  utxos: ["utxo1", "utxo2"], // Optional
  useFrozenUtxos: false // Optional
};

const spendingProposal = await spend(payload);

```
