# Completed proposals

We define a 'Completed Proposal' as a Nostr event with Kind '9292' that (in its encryped content) contains a Bitcoin transaction.
A completed proposal can only be created when the proposal has been approved (signed) by all the participants.

## Creating a Completed Proposal

To create a Completed Proposal, we use the 'finalizeSpendingProposal' method.

```javascript
const completedProposal = await smartVaults.finalizeSpendingProposal(proposalId);
```

The completedProposal object contains the transaction ID of the Bitcoin transaction that was broadcasted.
When the Completed Proposal is created, the associated Proposal is automatically deleted. If you decided to use frozen UXTOS, the proposals that share the same UTXOs will also be deleted.
