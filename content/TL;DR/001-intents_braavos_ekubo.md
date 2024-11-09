---
title: 'TL;DR #001 – Intents; Braavos; Ekubo'
date: 2023-10-12T10:02:06+02:00
weight: 999
draft: false
description: 
Tags: 
 - DeFi
 - Starknet
 - Layer 2
author: cleminso
ShowBreadCrumbs: true
---

## Intents aren’t real? 

[Source](https://twitter.com/DavideCrapis/status/1684685723742715904) from [@DavideCrapis](https://twitter.com/DavideCrapis)

- What's action preference type? How many dimensions are implicated? what's measurable (max $)? ⇒ which risks?

- What's a constraint type? satisfaction with risk and outcome?

- Why we use the current system? for which outcome? what's your preference for this system? What's your current preference? How is measure the outcome? ($?)

=> We use the current system because we accept setting our own income and accept a range result for the outcome in $.

- With intent, the solver has to know my preference vector in order to do a good job. [AGI](https://actualiteinformatique.fr/intelligence-artificielle/definition-artificial-general-intelligence-agi) raining possible about my history.

- What does this mean in practice?

"*Users and their preferences are real. Discovery is key if we want to go beyond a simple application. In the short term, standard tools, templates, and mechanism for solving specific classes of intent commitments are more important than dreams.*"

--- 

### How Braavos on Starknet is revolutionizing crypto signing
[Source](https://starkware.medium.com/how-starknet-is-revolutionizing-crypto-signing-ba3724077a79)

For context, public blockchains **secp256k1 elliptic curve** cryptographic signature schemes. But it's **not compatible** with the cryptographic signature scheme available in mobile devices with Hardware Security Modules (HSM), such as the iPhones and Android (Pixel and other) phones.

Mobile devices use the curve secp256r1 (also called NIST-P256) and Starknet doesn't support secp256r1, has its own proprietary curve, which is a STARK-friendly curve, and supports AA natively.
⇒ Braavos use it to introduce Hardware Signer

**→ Hardware Signer – 2 Main components**

- The secure sub-system in the user's mobile device

    - built-in in the user's device — the iPhone’s **Secure Enclave** or Android Phone’s **Titan HSM** to protect their account

    - There are dedicated and isolated sub-system, totally separated from the application processor, that can generate private keys and sign messages. **Keys are generated** by an internal True Random Number Generator and **sign messages** over the secp256r1 elliptic curve via its internal Public Key Accelerator.

    - **private keys never leave the secure system and are unknown or inaccessible to anyone, not even to the user, or to the application itself.**

- The account smart contract that can run arbitrary logic (=AA)

    - The **client side** (e.g. the application) that allows the user to review or sign transactions and send them to the chain.

    - The **on-chain side** — has an account smart contract that can run arbitrary logic; and in particular, in our case, run arbitrary signature **verification** logic.

⇒ The application signs the transaction using the mobile device security module and then sends it to the account contract on-chain that can verify it. This means that even the actual approval to sign a transaction is done directly.

**→ Solutions**

- **Biometric** – it supports intrinsically biometric authentication of the user identity

- **Recovery** – 2 Keys

    - **Hardware Signer Keys** → used to sign all transactions

    - **Key derived from the seed phrase** → can only sign this one transaction "Request to remove Hardware Signer” with a 4 day delay in rejecting this request.

    - *This means that if the device gets stolen, lost, or bricked, users will still be able to recover their account within 4 days. However, if their Seed Phrase gets stolen and an attacker issues a request to remove the Hardware Signer, the user will automatically (and repeatedly) get a notification on their mobile device and will be able to cancel the request and keep all the assets safe.*

--- 

### Ekubo

[From Ekubo documentation
](https://docs.ekubo.org/about-ekubo/introduction)

**Gas Efficiency** → Ekubo uses the ["till" pattern](https://docs.ekubo.org/integration-guides/till-pattern) and a singleton design to provide the cheapest trades against concentrated liquidity. Introduce [here](https://www.youtube.com/watch?v=xFp8RlRq0qU) and describe [here](https://github.com/OpenZeppelin/openzeppelin-contracts/issues/4361#issuecomment-1595095135).

- pools are managed in a single contract, making tx more cost-effective & minimizing the required token transfer

*And when do I **swap against** a pool or **update** my position?* 

- token transfers are deferred until the end of the transaction. Aggregators could save them in Ekubo for later, avoiding expensive token transfers altogether.

⇒ The result is that you can **execute many actions across many pools** and only make the minimum number of required token transfers.

**Concentrated liquidity** → allows market makers to [provide liquidity](https://docs.ekubo.org/user-guides/add-liquidity) within a specified price range

- each LP choose the exact parameters of their positions = LP provider can restrict orders to a specific price range. Better-enhanced rates for swappers and LP allow them to use their liquidity efficiently.

- all position in a pool are aggregated from a swapper’s perspective

    ⇒ swappers get better pricing because liquidity providers can leverage up within a price range, or earn yield on unused capital elsewhere.

[Extensions](https://docs.ekubo.org/integration-guides/extensions) → allow third-party developers to permissionlessly create new kinds of pools on Ekubo

- integrate into the same ecosystem of aggregators and interfaces built on top of Ekubo

These pools can implement new features

- oracles

- order types

- TWAMM

**Withdrawal fee** → I pay a fee equal to the swap fee of the selected pool from your principal

It *decreases* as a percentage of *liquidity* as capital efficiency increases

It *decreases* as a percentage of principal + fees as fees are earned over time

Thus, the fee incentivizes all liquidity concentration, passive liquidity and low fees.

Ticks allow liquidity providers to set specific price points

Tick spacing optimizes the cost of swaps based on asset volatility.

**Flash accounting** enables internal token balance management before actual transfers, saving on gas fees. Also, allow free flash loans within the Ekubo ecosystem.
