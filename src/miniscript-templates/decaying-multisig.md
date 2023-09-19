# Decaying Multisig

## Description
Decaying multisig is a custody technique where the number of keys required to move the funds decreases over time. For example, a 3 of 3 multisig may decay to only need 2 of the 3 keys after 1 year, and then to 1 of the 3 keys after 5 years.

One use case for this is mitigating against loss of funds due to key loss. If a key is lost, the owner only needs to wait until the next decay step to recover the funds. Another use case is for losening consensus for co-managed assets. For example, a board of directors may generally require a higher threshold (67%) to spend funds, but decrease that over time (to 51%) to avoid allowing a subset of signers to deadlock the funds.

## Vault Configuration Example
All 3 signers are needed to spend. After 10,000 blocks, the `after` block meets one of the threshold's conditions, so only 2 signatures are needed to unlock the funds. Finally, after 20,000 blocks, 2 conditions are met by the `after` statements and only 1 additional signature is needed.
![image](https://github.com/smartvaults/smartvaults/assets/32852271/199630b1-8812-45ce-9d44-6f2a35e030e6)


## Inputs

- Threshold
- List of Signers (extended public keys)
- List of Lock times (integers)

## Miniscript

```
thresh(
    <threshold>,
    pk(key_1),
    pk(key_2),
    pk(key_3),
    ...
    after(lock_time_1),
    after(lock_time_2),
    ...
    )
```