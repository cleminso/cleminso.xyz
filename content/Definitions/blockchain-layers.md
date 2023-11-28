---
title: 'Blockchain & Layers'
date: 2023-11-26T10:02:06
weight: 2
draft: false
description: Discover straight-to the point definitions of blockchains and layers.
Params:
  - ShowBreadCrumbs: true
  - ShowPostNavLinks: true
tags:
    - Blockchain
    - Layers
author: cleminso
---

A blockchain records transactions into blocks that are linked by a **cryptographic hash** of the previous block, timestamp and transaction data. 

See hashes as a red line to connects all blocks in a blockchain. This line **ensure the data integrity** and **immutability** of each blocks in a blockchains. 

> A cryptographic hash is a mathematical reduction of a string, so that one hash of a string will always be the same.

Its importance lies in the fact that that if any data is modified, the hash would be different and will not recognize by the current consensus.

In the absence of these hashes, blocks can be reordered without detection and the data integrity is not valid anymore.

Thus, the blockchain can maintain a continuously growing chain of ordered blocks there one hash cannot represent the same string of data.

*Do you know where is from the capacity to maintain an ordered chain of blocks?*  
Is provided by the ledger.

> A **Ledger** communicates the idea of order and permanence. 

It's the logic that manages and brings properties to the database. Thanks to the ledger, it's impossible for a past event to be replayed. 

The benefits are the resistance to the modification of any data, the ability to record transactions between two parties, and the fact that it is verifiable and permanent.

---

Let's highlight the blockchain properties

The **decentralization** means that several unknowing actors are implicated in the system. 

> The system can survive if x actors are deconnected or attempt an attack against the system. 

The benefits are that it provides a trustless system where no single entity controls the system; anybody can contribute and build their own Dapps without permission.

A decentralized system necessary implied that system is distributed into several actors.  
But **distributed** doesn't imply the system is decentralized.

The **public** properties enable the system to be available and accessible to anyone.  
The benefits are that anybody can connect to one RPC network and read transparently, create a wallet, execute, and send transactions in the system.

---

*We often use Layer term to refer to Blockchain, but what are the difference? When we use Layer, we talk about what?*

> A layer is a blockchain that relies on the security of its parent blockchain to achieve full finality by consolidating its state into the parent layer.

Layers refer to **how blockchain networks address scalability**.

Some layers are dedicated to specific blockchain concepts like scalability; execution; and data availability. It's here that we enter an **interoperability** world based on a modular architecture.  
Layers have different security assumptions depending on their parent layer. That means the parent layer is more secure, and transactions from the child layer are settled and consolidated.

**Settlement** means the transactions are validated and recorded in the blockchain. At this point, the transactions are final and irreversible.

- From a users point of view, a layer is a blockchain with their own consensus.  
- Form the interoperability point of view, is two layers that can communicated together.

---

**Resources used**

https://en.wikipedia.org/wiki/Cryptographic_hash_function  

https://www.gemini.com/cryptopedia/blockchain-layer-2-network-layer-1-network#section-layer-1-scaling-solutions
