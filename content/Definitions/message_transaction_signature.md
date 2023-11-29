---
title: 'Message & Transaction & Signature'
date: 2023-11-29T0:00:00
weight: 5
draft: false
description: 
Params:
  - ShowBreadCrumbs: true
  - ShowPostNavLinks: true
tags:
    - Blockchain
    - Messaging
author: cleminso
---

*We know a [blockchain records transactions](https://cleminso.xyz/definitions/blockchain-layers/) into blocks that are linked by a cryptographic hash of the previous block. Let's focus on the transaction word and see how it's work.*  

*Why are message, transaction and signature in blockchain, and what are their relations?*

---

Imagine asking for or ordering a bank transfer for a friend:
- You need to provide your intent and the necessary data,
such as 'amount requested'  
=> message
- You need to send your intent in understandable words and provide the sender and receiver of the order => transaction
- the institution who execute, it needs to understand and ensure the transaction is legitimate => signature

*Let's compare it with what happens when users initiate an interaction with a blockchain.*
1. The user sends an encrypted message that contains data
	- sender and recipient address (from and to) 
	- message data (value)
	- the gas token amount to transfer alongside the message
2. This message is embedded into a transaction
3. This transaction is broadcast to the network with a signature
4. The virtual machine (VM) takes this signature to ensure a match between the signature and the text (data message)
5. The VM extracts the sender addresses (public key) to ensure a match between the signature and the sender
	- that the 'from' when we look into an explorer  

=> All is extracted from the signature broadcasted into the network, so nothing is from a third party (which limits attack vectors and invalid data).

---

### Message

>  A message is a **data container** of the user intention wishes to execute and that will be processed by the blockchain

In EVM, a message is a data and value container, and it is only unlocked and executed by smart contract if certain conditions are met.
Sending a message can be initiated by users via a smart contract or directly by the smart contract itself.

*As the message included in a transaction, and that a transaction is recorded on the blockchain and therefore immutable. Messages inherit this property.*

---

### Transaction

> A transaction is an **execution of code** on the virtual machine, containing the message to be executed.

As in the previous example, this is how the bank transfer will be executed, from and to which bank address. And the third party executes the intent.   
But with blockchain, it is executed in a decentralized way via smart contracts.

**What does execution mean for blockchain?**  

> An execution is the process of validating and adding transactions to the blockchain.

**What are the execution consequences for the blockchain?**  

That will engender:
- a blockchain **state change**
	- blocks is an ordered list of executions that will change the ordered state.
- a **balance change** for the sender and receiver
	- a balance is a number in a list that links to an address; for example, ERC-20 standardizes that.

---

### Signature

A signature doesn't only express how to interact with a blockchain but also provides an allowance to interact with the user's balance and tokens.

> A signature is a **proof of the allowance** of an authorization to execute an intention in a blockchain.

For example, swap USDC for ETH. The user's needs to sign an approval that authorizes a smart contract to access and execute the provided intent (swap) with their funds.

Also, signing a message before initiating a transaction **provides cryptographic proof** that the transaction was authorized by the sender.
The core purpose of signing in this context is to **confirm identity and ownership** rather than send a message.

If the signature execution is signed by the sender to execute a pre-defined interaction with a blockchain,
