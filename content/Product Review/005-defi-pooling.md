---
type: post
title: '005 - DeFi Pooling Review'
date: 2023-11-14T10:02:06+02:00
draft: false
description: Interact with L1 from L2!
weight: 995
aliases:
  - /first
tags:
  - DeFi
  - Starknet
author: cleminso
showToc: true
TocOpen: false
hidemeta: false
comments: false
canonicalURL: https://canonical.url/to/page
disableHLJS: true
disableShare: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
---

Blockchain scalability is limited. We can use a centralized operator for unlimited scalability, but that requires trusting the integrity of this operator. For newcomers, Centralized Exchange (CEX) are often the first way to interact with crypto. Their values reside in the way they abstract the complexity of technology (wallet key management, for example). But this is like using a bank account. 

The user doesn't control and own their funds; funds can be removed or frozen; and you need to prove your identity (so you lose your anonymity). The consequences are that all of your actions are traceable and associated with your identity.

To contrast, in DeFi you're the owner of your wallet keys. That means you have the responsibility of your funds, you can manage; deploy it where and when you want. The risk is to lose your seed phrase, a compromise of your private keys, or interact with a scam contracts. But enter in DeFi, open new perspectives.

## Jump into DeFi

DeFi exists to be a decentralized alternative to traditional financial actors without the need to trust an intermediary. Built on top of blockchain and smart contract technology. DeFi has the goal of making the financial system more transparent and accessible.

In other words, DeFi refers to financial Decentralized Applications (DApps) using Blockchain technology that inherit 
these properties and values.

### What are the DeFi benefits?

- The decentralization allows censorship resistance; anyone can participate.
- Network effects by integrating or supporting DApps, together
- Inheritance of Blockchain infrastructure benefits; fast and "low cost" transactions; immutability of smart contracts; noncustodial ownership

It's nice, but only in theory. The ecosystem is still growing and needs to search for its marks. It's through testing that we can innovate and learn from empirical experiences like life.

### DeFi has some requirements

- Scalability to support several users at the same time and for a long period
- Fast and low transaction costs to provide a better UX than traditional finance
	- the blockchain state is often updated (we talk in seconds).
	- we refer to the state by block or batch for Layer 2.

These requirements are exactly the current pain points for actual and future users if we stay on Ethereum (L1).
L1 has all the security benefits to support a financial system. But L1 doesn't have a good UX, so let's introduce to Starknet L2 and DeFi Pooling System.

## Starknet and DeFi Pooling

Layer 2's are the closest solutions to scaling Ethereum. While being built on top of Ethereum, they inherit the Ethereum security.

This is a fast explanation of Starknet and how transactions work:
- off-chain **Prover**:
	- process a **batch of transactions** and prepare a system **state update**
	- It also **generates a STARK proof**. The Prover sends it to the on-chain Verifier
- on-chain **Verifier**: receive the system state update and the STARK proof
	- the **proof is verified** to be valid, and only when the state update be committed on-chain

Starknet scales by **moving the transactions execution off-chain** and attesting the execution **integrity on-chain** with a STARKs proof.

Simple to said, but to truly understand that require to understand STARK proof, and it's long, haha. Resources are available on the [StarkWare site](https://starkware.co/stark*/).

All of that to store the data on L1. That allows developers to consume this data, but why would they want to do that? 

Imagine **interacting with L1 DeFi protocols from L2**, let's introduce DeFi Pooling.

### How does DeFi Pooling work?

Through [Starknet L1-L2 messaging](https://docs.starknet.io/documentation/architecture_and_concepts/Network_Architecture/messaging-mechanism/), contracts on L2 can interact asynchronously with contracts on L1.
With L1-L2 messaging, it's possible to:
1. **Talk with L1** by sending a message and by calling send_message_to_L1
	- the message parameters contain the recipient contract on L1 + relevant data
2. Starknet node operators (Prover and Verifier) will **generate a STARK proof** for these messages and **verify the validity**
3. When the transaction is proved and the L1 state is updated, the message is stored on L1 in the Starknet Core Contract
4. The L1 recipient address can now **Consume** the message in the Starknet Core Contract

Well, it's based on the same principle to understand theL1-L2 liquidity.

### How Liquidity moves on between L1-L2

On [StarkGate](https://starkgate.starknet.io/), each token is associated with an L1 and L2 bridge contract, and they communicate through the L1-L2 messaging mechanism.

The most important details to know about, how StarkGate works are the **mint & burn mechanisms**:
- When users **initiate a deposit** via StarkGate; a function is called **to mint** the corresponding token for the users.
- When users **initiate a withdraw** via StarkGate; a function is called to burn the corresponding token from the balance of L2 users.
The power of this system is that **liquidity always resides on L1**! and all transactions are attached to a STARK proof with which we can verify their validity.

By the way, that allows other features, like [Escape Hatch](https://docs.starkware.co/starkex/perpetual/forced-actions-escape-hatch-perpetual.html), to allow users to directly withdraw from L1 (in case the system has problems).

After all, it's designed to meet user needs and solve existing pain points. 
In the next review, let's study Nimbora, a project, rather than push DeFi Pooling, into production.

## Product Suggestions

---

### Open liquidity management

We can imagine a world powered by messaging + STARK proof to attest to the integrity of any messages/transactions.

Now L2 is your dashboard. Manage and communicate with L1 and others Rollup's (always using L1 messaging).


The idea is to stop liquidity fragmentation. We can imagine interacting with Arbitrum from Starknet using Ethereum. 

  Starknet ⟷ Ethereum and Ethereum ⟷ Arbitrum

Furthermore, we can imagine doing that with private chains such as Aztec. Initiating your on/off ramp from Starknet but using this liquidity on a private network, or the other way around.

*Of course, that requires a strong messaging mechanism from these L2s.*

Imagine **customizing** your L3 for specific functionalities and **specialized applications**.

Moreover, create, communicate, and interact with L3. You can create your own private L3 [Madara](https://www.madara.zone/) or app chain [Karnot](https://www.karnot.xyz/) based on your needs.

Create a data storage place. Request data from another chain, relay it,, share it where you want.

### Stop Bridge, say hello to messaging!

Imagine no more bridges, only messaging between chains. Stop the need to deploy token contracts on a new chain and increase liquidity fragmentation. With messaging, deploy a Verifier contract and proof the integrity from L2, with a STARK proof.

Like this, assets live on one chain. To move on another chain, the messaging bridge uses mint & burn mechanisms and a call function to send the token to the corresponding users.

We know that bridges are vulnerable to security breaches and are the target of numerous hacks.

### Gas Delegation

The idea is to enable users to create a gas tank on L2 and deploy it where and when they want.

At the protocol level, there is an arbitrage on the gas. For users, there is a de-fractrionalization of gas and an UX improvement.

Imagine executing a transaction during a high Gwei peak.

[A good place to improve this idea](https://gastoken.io/)
