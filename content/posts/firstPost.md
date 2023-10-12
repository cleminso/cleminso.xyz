---
title: 'TL;DR #001 – Intents; Braavos; Ekubo'
date: 2023-10-12T10:02:06+02:00
draft: true
---

### [Intents aren’t real?](https://twitter.com/DavideCrapis/status/1684685723742715904) from [@DavideCrapis](https://twitter.com/DavideCrapis)
- What's action preference type? How many dimensions are implicated? what's measurable (max $)? ⇒ which risks?

- What's a constraints types? satisfactions of risk and outcome?

- Why we use the current system? for which outcome? what's your preference with this system? What's your current preference? How is measure the outcome? ($?)

=> we use the current system because we accept to settings ourself the income and accepted a range result for outcome in $.

- With intent, the solver has to know my preference vector in order to do a good job. [AGI](https://actualiteinformatique.fr/intelligence-artificielle/definition-artificial-general-intelligence-agi) raining possible about my history.

- What does this mean in practice?

*Users and their preferences are real. Discovery is key if we want to go beyond a simple application. In the short term, standard tools/templates/mechanisms for solving specific classes of intent commitments are more important than dreams.*

--- 

### [How Braavos on Starknet is revolutionizing crypto signing](https://starkware.medium.com/how-starknet-is-revolutionizing-crypto-signing-ba3724077a79)

For context public Blockchain use **secp256k1 elliptic curve** cryptographic signature schemes. But it's **not compatible** with the cryptographic signature scheme available in mobile devices Hardware Security Modules (HSM), such as the iPhones and the Android (Pixel and other) phones.

Mobile Devices use: curve secp256r1 (also called NIST-P256) and Starknet don't support secp256r1, has its own proprietary curve which is a STARK-friendly curve and support AA natively. 
⇒ Braavos use it to introduce Hardware Signer

**→ Hardware Signer – 2 Main components**

- The secure sub-system in users mobile device

    - built-in in users device — iPhone’s **Secure Enclave** or Android Phone’s **Titan HSM** to protect their account

    - There are dedicated and isolated sub-system, totally separated from the application processor, that can generate private keys and sign messages. **Keys are generated** by an internal True Random Number Generator and **signs messages** over the secp256r1 elliptic curve via its internal Public Key Accelerator.

    - **private keys never leave the secure system and are unknown/inaccessible to anyone, not even to the user, or to the application itself.**

- The account smart contract that can run arbitrary logic (=AA)

    - The client side (e.g. the application) that allows the user to review/sign transactions and send them to the chain.

    - The on-chain side — has an account smart contract that can run arbitrary logic; and in particular, in our case, run arbitrary signature verification logic.

⇒ The application signs the transaction using the mobile device security module and then sends it to the account contract on-chain that can verify it. This means that even the actual approval to sign a transaction is done directly

→ Solutions

- Biometric – it supports intrinsically biometric authentication of the user identity

- Recovery – 2 Keys

    - Hardware Signer Keys → used to sign all transactions

    - Key derived from the seed phrase → can only sign this one transaction "Request to remove Hardware Signer” with 4 days delay rejecting this request

    - *This means that if the device gets stolen/lost/bricked, users will still be able to recover their account within 4 days. However, if their Seed Phrase gets stolen and an attacker issues a request to remove the Hardware Signer, the user will automatically (and repeatedly) get a notification to their mobile device and will be able to cancel the request and keep all the assets safe.*

