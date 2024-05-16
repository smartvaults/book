
<div align="center">
  <img src="../SV-Logo-Vertical-Black.svg" width=400/>
</div>

# Inheritance: What will happen to your bitcoin when you are gone?

## Introduction

You've worked hard to build your wealth in bitcoin. But have you thought about what will happen to your digital assets when you're no longer around? It's essential to create a plan to ensure your loved ones can access and benefit from your bitcoin inheritance. In this article, we'll discuss the importance of planning for your bitcoin's future, the challenges you might face, and the solution Smart Vaults offers.

Why You Need a Plan for Your Bitcoin Inheritance:

Bitcoin doesn't have a central authority or intermediary to help transfer ownership when someone passes away. That's why it's up to you to make a plan for your loved ones to access your digital wealth. A well-thought-out plan can prevent confusion and make sure your bitcoin goes to the right people. Without one, your digital assets could become inaccessible, and your beneficiaries might miss out on the value you've built.

Leaving bitcoin to your loved ones can be tricky due to its unique features. Here are some issues you might encounter:

- Understanding Instructions: Bitcoin can be complex, and your beneficiaries might not be familiar with how it works. Without clear instructions, they might struggle to access and manage your digital assets.

- Keeping Instructions Safe: It's crucial to protect your bitcoin inheritance from unauthorized access. If your instructions fall into the wrong hands, your digital assets could be at risk of theft or misuse.

The Solution: Smart Vault's Inheritance Vault

At Smart Vaults we offer you a solution to these challenges. Our Inheritance vault uses [Miniscript](https://smartvaults.github.io/book/articles/intro-to-ms-en.html) to create a secure [inheritance logic](https://smartvaults.github.io/book/miniscript-templates/social-recovery.html) for your bitcoin holdings.

By using Smart Vault's Inheritance template, you can set up a secure inheritance plan that ensures your loved ones can access your bitcoin only after a predetermined period. This approach simplifies the process, provides clear instructions, and adds an extra layer of security to protect your digital assets from unauthorized access.

Planning for the future of your bitcoin is essential to ensure your loved ones can benefit from your digital legacy. By creating a clear plan and with Smart Vault's Inheritance vault, you can make it easier and safer for your beneficiaries to access and manage your digital wealth. Don't let your hard-earned bitcoin go to waste – start planning today and secure your bitcoin inheritance with Smart Vaults.

## Creating your first Inheritance Vault

In the following guide, we will assume you have already installed the Smart Vaults iOS app, created an account and added some contacts. If you haven't done so yet, you can find the (beta) app on [TestFlight](https://testflight.apple.com/join/1CFTiTXh).

for a step-by-step guide on how to add contacts and share signers, you can watch the following video:

<div align="center">
     <iframe width="450" height="315" src="https://www.youtube.com/embed/XDfBl4S_6R8?si=GHYDuf2CcSplWRur" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

To create a Inheritance vault using the Smart Vaults iOS app, follow these steps:

1. Navigate to the Vaults tab by clicking the plus icon located on the right upper corner of your screen.

     <div align="center">
       <img src="https://github.com/smartvaults/smartvaults/assets/71672123/b84cb17d-8bfa-4bd8-ad96-ffe7e1ad87b5" width=450/>
     </div>

1. Select the Inheritance Template.

     <div align="center">
       <img src="https://github.com/smartvaults/smartvaults/assets/71672123/5e54a25f-3eb0-4bd5-8a8c-d22517262b3b" width=450/>
     </div>

1. Define the name and description for your vault and choose the signer you wish to use (if you have more than one).

     <div align="center">
       <img src="https://github.com/smartvaults/smartvaults/assets/71672123/ff64104b-3afb-458d-ad20-55d767806b51" width=450/>
     </div>

1. Define the inheritance keys and the date in which the signatures of those keys become valid.

     <div align="center">
       <img src="https://github.com/smartvaults/smartvaults/assets/71672123/f12c3681-7f36-4a13-979c-02624b81ee7c" width=450/>
     </div>

     <div align="center">
       <img src="https://github.com/smartvaults/smartvaults/assets/71672123/eaf07c76-8728-472c-80f2-79fd6df1b997" width=450/>
     </div>

1. Define the number of inheritance signatures needed to move or make use of the bitcoin (threshold), finally create the vault.

     <div align="center">
       <img src="https://github.com/smartvaults/smartvaults/assets/71672123/15a06d16-4d42-4380-95b2-eb7719848cd8" width=450/>
     </div>

1. Congratulations! You have successfully created your first Inheritance vault.

     <div align="center">
       <img src="https://github.com/smartvaults/smartvaults/assets/71672123/d928f7cf-4e74-469e-ac94-44025e152093" width=450/>
     </div>

## Advanced Features

At Smart Vaults, we understand that planning for your bitcoin inheritance is a complex process and that you might have specific requirements. That's why we offer advanced features such as our policy vault editor, which allows you to create custom policies tailored to your needs.

As an advanced user, you can define complex rules and conditions for your bitcoin inheritance, ensuring that your digital assets are managed according to your wishes. With Smart Vaults, you have the flexibility to create a personalized inheritance plan that meets your unique requirements.

In the following example, we'll show you how to create a custom policy for your Inheritance vault.

Let's suppose you want to move all your bitcoin to your inheritance vault to ensure your loved ones can recover it after a specific period if something happens to you, but you also plan to move small amounts of bitcoin for daily expenses. To achieve this, a vault created using the Inheritance template could be enough, but it won't be the most efficient solution. To understand why, we encourage you to read our article on [Miniscript](https://smartvaults.github.io/book/articles/intro-to-ms-en.html#probabilities-and-optimization), but to summarize, the Inheritance template doesn't make any assumptions about the probability of each spending condition. In our case, we know that the probability of moving small amounts of bitcoin for daily expenses is much higher than the probability of using the inheritance keys after the specified date, so we can optimize the vault to reduce the cost of using it for daily transactions, so let's do that.

To create a custom policy for your Inheritance vault, follow these steps:

1. Navigate to the Smart Vaults [Testnet](https://test.smartvaults.app) or [Mainnet](https://smartvaults.app) Web App.

     <div align="center">
          <video width="450" controls>
          <source src="https://github.com/smartvaults/smartvaults/assets/71672123/4b109d1f-6b9e-4a46-b0f5-fba92f926be3" type="video/mp4">
          </video>
     </div>

1. Click on the New Vault button located on the right upper corner of your screen. At the bottom of the vault templates list, you'll find the Custom Vault option. Click on it.

     <div align="center">
          <video width="450" controls>
          <source src="https://github.com/smartvaults/smartvaults/assets/71672123/3c7e8ee7-61ed-4f64-9e57-0cbda0406eb1" type="video/mp4">
          </video>
     </div>

1. Load the signers you want to use in your vault. In this case, we'll use the same signers we used in the Inheritance vault.

     <div align="center">
          <video width="450" controls>
               <source src="https://github.com/smartvaults/smartvaults/assets/71672123/908c267b-abeb-4f86-8566-8742ba3b2ef6" type="video/mp4">
          </video>
     </div>

1. Drag and drop the signers and the timelock to the policy editor.

     <div align="center">
          <video width="450" controls>
               <source src="https://github.com/smartvaults/smartvaults/assets/71672123/20ff05fc-4b0b-407d-8d77-3f9647738da0" type="video/mp4">
          </video>
     </div>

1. Define the spending conditions for your vault. In this case, we'll create two spending paths: Alice's signature (this will be the more likely path) and the inheritance path, notice that we define the former path as 100 times more likely than the later.

     <div align="center">
          <video width="450" controls>
               <source src="https://github.com/smartvaults/smartvaults/assets/71672123/35d5708b-3180-4ae8-85c6-f81e5db6dc99" type="video/mp4">
          </video>
     </div>

1. Choose a name and description for your vault and click on the save button.

     <div align="center">
          <video width="450" controls>
               <source src="https://github.com/smartvaults/smartvaults/assets/71672123/a8e14bf4-b3aa-460e-9ffd-a2bf842544cc" type="video/mp4">
          </video>
     </div>

1. Congratulations! You have successfully created a custom Inheritance vault.

     <div align="center">
       <img src="https://github.com/smartvaults/smartvaults/assets/71672123/b555258c-f189-4ccc-ad26-d2eaaec88216" width=450/>
     </div>

This is just one example of how you can use Smart Vaults' advanced features to create a custom policy for your bitcoin inheritance. With our flexible tools, you can design a personalized inheritance plan that meets your unique requirements and ensures your digital assets are managed according to your wishes.
