
<div align="center">
  <img src="../SV-Logo-Vertical-Black.svg" width=400/>
</div>

# Social Recovery: Do you want to self-custody your bitcoin but are afraid of losing access to it?

<p align="center">
<img src="https://github.com/smartvaults/smartvaults/assets/71672123/1ee8d43e-0e94-46c1-a22c-af8f99f3a3de" width="400"/>
</p>

## Introduction

Bitcoin custody comes with its own set of challenges and risks, regardless of whether you choose self-custody or third-party custodians. While third-party custodians can alleviate some burdens, the risks of hacking, mismanagement, or insolvency can be more likely and potentially lead to the loss of your Bitcoin. Smart Vaults offers a self-custody solution that focuses on mitigating these risks and providing you with full control over your Bitcoin.

Self-custody of Bitcoin involves storing your digital assets in a wallet that only you have access to. This means that you are solely responsible for safeguarding the private keys that unlock your wallet. While this level of control offers autonomy, privacy, and direct ownership, it also introduces the "key management problem." If you lose these keys, you lose access to your Bitcoin, and there's no central authority or customer service to help you recover it.

Smart Vaults is an easy-to-use and powerful open-source Bitcoin application designed to guide you through the process of creating and managing secure vaults for your Bitcoin. The app offers various vault templates tailored to different use cases, but for those worried about losing access to their Bitcoin, the Social Recovery Template stands out as a self-custody solution.

It's worth noting that the "Social" part of the Social Recovery Template can be as social as you want it to be. The recovery keys you define can belong to any person you want, including yourself.

The Social Recovery Template is a self-custody solution that helps you ensure you never lose control of your Bitcoin. With this vault template, you can:

- Define any number of recovery keys.
- Specify the time that needs to elapse before the signatures of those keys become valid.
- Specify the number of recovery signatures needed for recovery.

So, in the unfortunate [but possible](https://www.nytimes.com/2021/01/13/business/tens-of-billions-worth-of-bitcoin-have-been-locked-by-people-who-forgot-their-key.html) scenario where you lose access to your keys, the recovery cosigners you defined when creating the vault can help you recover your Bitcoin after the specified period of time has passed.

The Social Recovery Vault mitigates the key management problem by distributing the responsibility of key safekeeping among trusted individuals. These guardians do not have any control over your Bitcoin before the specified time has elapsed, and even after the time has passed, any transaction will need to have the required number of signatures you defined. This way, you maintain full control over your assets while having a safety net in case of key loss or technical errors.

In conclusion, Smart Vaults' Social Recovery vault is a self-custody solution designed for those who want to enjoy the benefits of autonomy, privacy, and direct ownership without constantly worrying about losing their keys or encountering technical issues. By choosing Smart Vaults, you prioritize self-custody above anything else, effectively managing the associated risks while maintaining full control over your Bitcoin.

With Smart Vaults, you can step into the world of Bitcoin self-custody with confidence.

## Creating your first Social Recovery Vault

In the following guide, we will assume you have already installed the Smart Vaults iOS app, created an account and added some contacts. If you haven't done so yet, you can find the (beta) app on [TestFlight](https://testflight.apple.com/join/1CFTiTXh).

for a step-by-step guide on how to add contacts and share signers, you can watch the following video:

<iframe width="750" height="315" src="https://www.youtube.com/embed/XDfBl4S_6R8?si=GHYDuf2CcSplWRur" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

To create a Social Recovery Vault on the Smart Vaults iOS app, follow these steps:

1. Navigate to the Vaults tab by clicking the plus icon located on the right upper corner of your screen.

![SR-new-vault](https://github.com/smartvaults/smartvaults/assets/71672123/b84cb17d-8bfa-4bd8-ad96-ffe7e1ad87b5)

1. Select the Social Recovery Template.

![SR-choose-template](https://github.com/smartvaults/smartvaults/assets/71672123/083361bc-86fc-4a4d-9943-157abfdfd760)

1. Define the name and description for your vault and choose the signer you wish to use (if you have more than one).

![SR-name-desc](https://github.com/smartvaults/smartvaults/assets/71672123/5c253fb0-087f-46cc-a703-85c66d2d3e50)

1. Define the recovery keys and the time that needs to elapse before the signatures of those keys become valid.

![SR-add-cosigners](https://github.com/smartvaults/smartvaults/assets/71672123/fb816b38-7273-49b7-8ecf-63d57f120e9f)

![SR-activation-period](https://github.com/smartvaults/smartvaults/assets/71672123/9fdb5543-f502-4b00-bed2-e9aed3b405ab)

1. Define the number of recovery signatures needed for recovery (threshold), finally create the vault.

![SR-threshold](https://github.com/smartvaults/smartvaults/assets/71672123/30e0d076-fde6-4c1d-931c-8bc79d035b6b)

1. Congratulations! You have successfully created your first Social Recovery Vault.

![SR-done](https://github.com/smartvaults/smartvaults/assets/71672123/01af7911-ad64-4040-a31e-6f257a366271)
