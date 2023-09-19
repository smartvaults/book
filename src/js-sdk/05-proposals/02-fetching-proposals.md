# Fetching Proposals

## Overview

The Smart Vaults JS library  provides multiple methods for fetching proposals.

## Available Methods for Fetching Proposals

### 1. `getProposals()`

This method fetches all proposals without any filters.

```javascript
const proposals = await smartVaults.getProposals();
```

Of course, you can also use it with pagination options.

```javascript
const newProposals = await smartVaults.getProposals({since: someRecentDate });
```

### 2. `getProposalsById(proposalIds: Array)`

Fetches proposals based on their IDs.

```javascript
const specificProposals = await smartVaults.getProposalsById([someProposalId, anotherProposalId]);
```

### 3. `getProposalsByPolicyId(policyIds: Array)`

Fetches proposals based on their associated policy IDs.

```javascript
const policyBasedProposals = await smartVaults.getProposalsByPolicyId([somePolicyId, anotherPolicyId]);
```
