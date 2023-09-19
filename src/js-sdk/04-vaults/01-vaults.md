# Vaults

There cannot be Smart Vaults without Vaults. In this section, we will learn how to create and manage vaults. We start with some definitions.

1. **Vault** is a Bitcoin Wallet.
2. **Policy** is a set of rules that define how a vault can be managed.
3. **Vault Template** is Vault with a predefined Policy.

While it is true that a Policy is not exactly the same as a descriptor, we define the `Policy event` as a Nostr event with kind `9289` that (in its encryped content) contains a descriptor.
