# Approvals

We define an `Approval` as a Nostr event with kind `9291`, that (in its encryped content) contains a signed PSBT. Currently, an approval can be created in two ways:

1. Using the Smart Vaults desktop app.
2. Using the Smart Vaults iOs app.

## Approvals and signers

An approval can only be created using a valid signer. The valid signers are defined in the policy of the vault from which the proposal was created.

## Approvals and proposals

An approval is always associated with a proposal. The proposal can only be finalized when all the required approvals are created.

## Fetching approvals

To fecth approvals, you can use the 'getApprovals' method.

```javascript
const approvals = await smartVaults.getApprovals();
```

This method retrives all the approvals that you or the members your vaults have created.

## Fetching approvals associated with a proposal

In practice, you will want to fetch the approvals associated with a given proposal. To do so, you can use the 'getApprovalsByProposalId' method.

```javascript
const approvals = await smartVaults.getApprovalsByProposalId(proposalId);
```

## Approvals and proposal status

When you fetch a proposal, you can see the status of the proposal. The status can be one of the following:

1. 'Unsigned': The proposal has not been signed by all the required signers.
2. 'Signed': The proposal has been signed by all the required signers.
