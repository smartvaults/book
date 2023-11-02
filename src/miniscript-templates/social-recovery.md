# Social Recovery Template / Inheritance

## Description

Social recovery keeps you in full and exclusive control of your bitcoin while enabling a recovery path in case you lose your keys. After a predefined number of months set by the user, an m of n multisig of trusted co-signers is able to move the user funds

Between 20%-25% of all bitcoin has been lost forever by owners who lost their keys. This security feature helps you have a plan B, leveraging trusted connections like friends, family, or colleagues to regain access to your Bitcoin

## Vault Configuration Example

TODO

## Inputs

* Signer keys (extended descriptor): 1 + N for recovery
* Timestamp or block height if using an absolute timelock (`after`), number of confirmed blocks if using relative timelock (`older`)

## Miniscript

```
or(1@pk(Key1),1@and(thresh(2,pk(RecoveryKey1),pk(RecoveryKey2)),after(TimestampOrBlockHeight)))
```

## Output Descriptor

```
tr(Key1,and_v(v:multi_a(2,RecoveryKey1,RecoveryKey2),after(TimestampOrBlockHeight)))
```

### Example

Example Output Descriptor

```
tr([7356e457/86'/1'/784923']tpubDCvLwbJPseNux9EtPbrbA2tgDayzptK4HNkky14Cw6msjHuqyZCE88miedZD86TZUb29Rof3sgtREU4wtzofte7QDSWDiw8ZU6ZYHmAxY9d/0/*,and_v(v:multi_a(2,[4eb5d5a1/86'/1'/784923']tpubDCLskGdzStPPo1auRQygJUfbmLMwujWr7fmekdUMD7gqSpwEcRso4CfiP5GkRqfXFYkfqTujyvuehb7inymMhBJFdbJqFyHsHVRuwLKCSe9/0/*,[f3ab64d8/86'/1'/784923']tpubDCh4uyVDVretfgTNkazUarV9ESTh7DJy8yvMSuWn5PQFbTDEsJwHGSBvTrNF92kw3x5ZLFXw91gN5LYtuSCbr1Vo6mzQmD49sF2vGpReZp2/0/*),after(840000)))
```
