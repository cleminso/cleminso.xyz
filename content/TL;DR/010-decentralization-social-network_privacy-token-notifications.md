---
title: 'TL;DR #010 - Decentralization for social network; Privacy token notifications'
date: 2024-01-20T00:00:00
weight: 990
draft: false
aliases: 
  - /tldr/010/ 
description: In this TL;DR, discover the challenges for decentralized network and how a push tokens can potentially deanonymize users?

Params:
  - ShowBreadCrumbs: true
  - ShowPostNavLinks: true
tags:
  - Social network
  - Privacy
  - Web3 Communities
---

## Sufficient Decentralization for Social Networks

Source: [Sufficient Decentralization for Social Networks](https://www.varunsrinivasan.com/2022/01/11/sufficient-decentralization-for-social-networks) by [Varun](https://twitter.com/varunsrin) from [Farcaster](https://twitter.com/farcaster_xyz).


### Challenging problems with decentralizing social networks

→ **Scaling networks** are a series of messages passed between users through a centralized server. 

- enable users to choose any server they like to store their messages and sign each one with a public/private key
- public key become a unique identifier for the user, and messages are tamper-proof

Alice {write message} → facetok server ⟷ {read message} Bob
Alice {write message} → Alice's server → {read message} Bob → {write message} Bob's server

**problem statement**:  
- users want their messages available to all followers, which requires an always on-server in the cloud. Self-hosting is complex and expensive as running your own website, is not viable

**solution** - managed hosts 
- companies host users' social data. users delegate actions they cannot do themselves

> But that a trap, this system enable a companie monopole and can block the service for users

→ **Decentralizing the name registry** importance to find the correct host to send and receive messages

- Name registry, can help to map every user's unique public key to a host URL, linked to a unique username.
	- allow alice to change this URL protects them against malicious hosts. If a host stops serving their messages, they can modify the registry to point to a new host, and followers will switch to the new location

Smart contract (SC) enable decentralize registries:
- user can make tx to a SC on a blockchain, that performs the functions of a decentralized registry
- the SC ensures that only that user can change the URL
- blockchain provide conflict resolution if two peoples try to register the same name simultaneously

Only the registry needs to be sync on a blockchain, all securely actions can happen off-chain by signing them with the key pair

→ **Building novel social primitives**

- users really want from a new social network is 8status8 or 8entertainment8, along with the benefits that decentralization offers.

The idea maze of things you can do with decentralized identities, blockchains and zk-proofs is large, weird and interesting enough that there are probably many primitives waiting to be discovered. Decentralized social networks should explore this as a way to attract users and offer a new product experience.

---

**Personal note**:

Centralized social networks decide for us what, how, and when we see content. We are no longer masters of our feed. With a decentralized network, we can aspire to build a better statement (with ambition) and regain control of our attention. 

We can do it with a simple RSS feed, but with the emergence of the current social network, this way of consuming content has decreased. Feeding (RSS or not) is more convenient for a microblog or newsletter.

*I currently read about Feed and try to shape a simple app that I would like to use*.

---

## Privacy of push notification

Source: [On the Privacy of Push Notifications](https://blog.phnx.im/privacy-of-push-notifications/).

How a push tokens can potentially deanonymize users?

> Push notifications are a mechanism through which applications can send and display notifications to users of smartphones. 

*UI is well know by user unlike the infrastructure, that drives them in the background is complex mechanism and not without privacy issues*.

Push.N <> Applications
- App must register a push token 
	- tokens are an identifier that references the installation of an App on a specific device
	- they are used as an identifier to route messaging from the internet to a device

### Privacy problems

**I - The notifications content is fully visible to hosted platform (deliberate design choice)**

Solution:
1. synchronize secret key material between the app server and the user device over TLS
2. use this key material to encrypt the content of push tokens

=> by design the key material is not accessible to push token platform, the content remains protected  
App developers can minimize the amount of data shared over push notifications

**II - The linkability of push tokens to the device account** - the platforms can therefore tie those to user accounts used in App*

Current state to show notifications to users:
1. app request push token from platform push notification service (Google, Apple's etc)
2. App require the push token whenever a notification is to be displayed on user device
	- must therefore hold on to that token for as long as users use the app

Process:
1. store the push token on the app server as part of a user account
2. notification is to be sent out the app server looks up the user's profile, find the associated push token
	- uses it to route the push notification to the user's device by the intermediate of the platform push notification service

**In summary:**

The push token is associated to:
- user account
- account or identifier of the concenerd platform (Google; Apple etc)

The push token **becomes part of user data** and that can be requested in the context of a legal warrant

Even when a user never provided any identifying information to the app, their anonymity is comprimised by the push token

### What platform can do?

How a system should be incapable to link push tokens to specific user data?
- use cryptographic has functions can create one way links that can't be traced back

To solve this issue, it result of the platform level, application developers cannot easily address the push token privacy issue. User's can use alternative platform service like UnifiedPush

**Solution in particulary use cases:**

- Push tokens are only stored in encrypted form on the application servers
- The key to decrypt them is stored on client devices (users’ phones and computers)
- The key is sent from the client to the server whenever a push notification is sent out and the server discards the key right after the notification is sent
Here app dev cannot provide data via push tokens, any longer the servers only hold the decryption key for what is typically a fraction of a second

**This approach has to prerequisites:**

1. Push notifications can only be sent out when the action is triggered on a user’s device
2. There needs to be a key management system that involves layers of key wrapping and a practical group key agreement mechanism

Use MLS as an encryption protocol. MLS serves as the key negotiation mechanism to easily obtain group keys in group chats

