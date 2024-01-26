---
title: '009 - Introduction to 0ptima protocol'
date: 2023-01-26T00:00:00
weight: 991
draft: false
description: 0ptima is a protocol where data is encrypted by default and anyone can create their own applications.
Params:
  - ShowBreadCrumbs: true
  - ShowPostNavLinks: true
tags:
  - Privacy
  - Protocol
  - My Project
---

The goal of this review is to:
- Introduction to 0ptima protocol: problem statement, why, and our personal frustations; introduction to tech solutions
- What is 0ptima + our values
- How our design chooses + missions  

Is it an exercise for me to express what we try to achieve with 0ptima. Is still incomplete and requires technical confirmation about our design, it's time to take the plunge!

---

Today, most systems, applications, and software are closed and cannot communicate together. That directly impacts the user's experience; that is, they are constrained by using a single client (front and back-end), and their data depends on this client. That means we can record and store our data on the internet but lose it at any moment by depending on centralized platforms and servers.

As users, we don't have control over our data - where it is stored, how it's used and consumed, etc. We are personally frustrated by the lack of control over and consent to our data when we subscribe to a software service or product. We are frustrated with having to reach across several platforms to achieve our goals and cannot quantify our experience or workflow. We are frustrated about the current business model of software applications. Why can't we pay for what we upload or consume? 

Fortunately, in the past decade, blockchain has appeared as a solution to build open and decentralized applications. A public blockchain means several unknown actors maintain the network, and the system can survive if x actors are deconnected or attempt an attack against the system. That looks like the perfect place to build a protocol where users keep control over their data!

---

## What is 0ptima?

> 0ptima is a protocol where data is encrypted by default and anyone can create their own applications.  

We are driven to build a decentralized and open protocol that enables participants to build their own economies and take advantage of the network effect by enabling interconnection between applications.

When we talk about ownership, we refer to the keys accessing the user's account and the data portability across the system. In 0ptima, data is stored at the protocol level (back-end) and consumed by the front-end client (if they have authorized access).     That enables users to choose between several front-end clients and find their data across all clients. In conclusion, neither the 0ptima protocol nor unauthorized clients can access the data of users.

In summary, 0ptima aspires to be an ecosystem of interoperable apps that can economically thrive while maintaining basic data rights.

**Our values** revolve around **decentralization** and **privacy**. We aspire to an open and personalizable web where minimizing trust is a core component. We can translate that into those properties:
- **Free control** and management of your own data (ownership) to enable better self-sovereignty
- **Fairness of resource distribution** among participants. That means participants are equal and have permissionless access to resources and applications across the system.
- **Cooperation** between actors to create a higher network effect and improve the user experience

---

## How we design 0ptima?

*We are still working on the protocol design; however, I can share what we have in mind. We hope for a first code release in March.*

In 0ptima, the main resource is the data. How data are available and move along the system. To enable data portability everywhere across the network, we need to have a standard data model in 0ptima.  
In other words, each application needs to know which language they speak and be able to read it.

Our wish is to design 0ptima as a system to push every participant to have the same opportunity for equality. Participants can start at a different moment but access the same resources across the 0ptima system and the existing user base.

Thereby, a data standard model enables collaboration between builders by integrating their app in a simple way. Imagine building a Twitter client; the bookmark feature is something asked by your users. Unfortunately, you don't have time to build one yourself, but someone can build an open bookmark plugin on 0ptima. You can integrate it into your client and satisfy the needs of your users.

By building on top of a public blockchain, 0ptima inherits those privileges and ensures the integrity and immutability of its users data. Our contracts are currently deployed on Gnosis, which will work as Auth and asset Ledger.

One of our values is ownership, which we achieve by using the [LIT Protocol](https://www.litprotocol.com/) as a key management and [access control](https://developer.litprotocol.com/v3/concepts/access-control-concept) system.
Basically, the LIT Protocol will grant the key to encrypt or decrypt a piece of content requested by the user and verify on-chain if the key has authorized access to a given piece of content. But where is the stored data?

Say hello to [Arweave](https://www.arweave.org/) and enter the permaweb!

In 0ptima, data is processed and accessible locally, but stored encrypted in the permaweb. That means your data is not dependent on a single server but is replicated across nodes into a decentralized network called Arweave. You can still access your data, even if 0ptima stops to live, because data is permanant forever (~200years). With the power of a decentralized storage system, your data is always under your control and accessible to you.

Our goal with 0ptima Protocol is to achieve an equilibrium between collaboration and customization while allowing builders to create their own economies. A simple and high-level model to describe it is:

> 0ptima value propositions + network effect → attract builder + incentives them to collaborate & compose together → will provide customizable UX

---

## Open Thoughts

We are in the early stages; nothing is ready to start building on top of 0ptima. We are working to provide an app test for Q2-Q3. If the tests are conclusive, we will work on how to deliver access for a small group of builders to interact with 0ptima and shape first applications :)

We haven't yet identified a target audience. We will start by building a small product to test and confirm the protocol structure.

**Our inspiration**:
- [hyperstructure](https://jacob.energy/hyperstructures.html) - for the economy protocol
- [farcaster](https://www.farcaster.xyz/) - the way they decentralized network
- [DXOS](https://dxos.org/) - for their open and collaborative software vision