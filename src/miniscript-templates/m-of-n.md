# Collaborative Custody Template

## Description

Collaborative custody allows users to configure the number of co-signers and the threshold required to access the vault’s bitcoin. 

Users can choose a 2 of 3, 3 of 5, or a custom configuration, this feature ensures that multiple trusted parties agree before a transaction takes place. It's an ideal solution for shared ownership and collaborative arrangements.

## Vault Configuration Example

TODO

## Inputs

* Threshold
* List of Signers (extended descriptor)

## Miniscript

```
thresh(
    <threshold>,
    pk(key_1),
    pk(key_2),
    pk(key_3),
    ...
)
```

## Output Descriptor

```
tr(InternalKey,thresh(3,pk(K1),s:pk(K2),s:pk(K3)))
```

### Example

Example Output Descriptor

```
tr(885db1e89516e0f0adc15ff8389320a01270a54f3b8ea4ecc705472904fc9a7e,multi_a(2,[7356e457/86'/1'/784923']tpubDCvLwbJPseNux9EtPbrbA2tgDayzptK4HNkky14Cw6msjHuqyZCE88miedZD86TZUb29Rof3sgtREU4wtzofte7QDSWDiw8ZU6ZYHmAxY9d/0/*,[4eb5d5a1/86'/1'/784923']tpubDCLskGdzStPPo1auRQygJUfbmLMwujWr7fmekdUMD7gqSpwEcRso4CfiP5GkRqfXFYkfqTujyvuehb7inymMhBJFdbJqFyHsHVRuwLKCSe9/0/*))#g52crz77
```
