# Hold Template

## Description

Hodl time locks let’s user set specific time intervals, with a maximum of 24 months, during which their bitcoin remains locked. 

The hodl time lock feature prevents impulsive selling during market fluctuations and allows users to stick to their investment strategy.

## Vault Configuration Example
To spend the funds, the second condition must be met, which involves an absolute timelock represented by `1701559661` in the example. 

This timelock will be satisfied after the specified time [1 month] has passed since the creation of this transaction.


![image](https://github.com/smartvaults/smartvaults/assets/88842056/5626c0ff-9351-427a-8bcf-86f33f441eb8)

## Inputs

* Signer key (extended descriptor)
* Timestamp or Block Height if using an absolute timelock (`after`), number of confirmed blocks if using relative timelock (`older`)

## Miniscript

```
and(pk(Key1),after(TimestampOrBlockHeight))
```

## Output Descriptor

```
tr(InternalKey,and_v(v:pk(Key1),after(TimestampOrBlockHeight)))
```

### Example

Example Output Descriptor

```
tr(e3e5c4a66d85841b9cea26793ef640bf7c1d26e759ae0296e643a16dad606c02,and_v(v:pk([7356e457/86'/1'/784923']tpubDCvLwbJPseNux9EtPbrbA2tgDayzptK4HNkky14Cw6msjHuqyZCE88miedZD86TZUb29Rof3sgtREU4wtzofte7QDSWDiw8ZU6ZYHmAxY9d/0/*),older(10000)))#e4gyn573
```
