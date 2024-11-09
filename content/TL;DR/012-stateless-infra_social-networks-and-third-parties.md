---
title: 'TL;DR #012 - Stateless Infra, Social networks and third-parties'
date: 2024-02-16T00:00:00
weight: 988
draft: false
aliases: 
  - /tldr/012/ 
description: In this TL;DR, what and why Stateless Infrastructure, the relation between social networks and their third-parties.
tags:
  - Social network
  - Blockchain
  - Protocol
ShowBreadCrumbs: true
---

## Stateless Infrastructure

Source [Stateless Infra](https://polynya.mirror.xyz/MChed2Qo4aiD7zwgWvGNpkCXmUbESCf7stjJe2h_TRk) from [Polynya](https://warpcast.com/polynya)

### What is Stateless Infrastructure
---

*For this blog: stick with blockchain = any chain achieving real-time strict global consensus (including rollups); stateless infra = not a chain, no consensus (or loose consensus), but decentralized complements that interact with the above mentioned blockchains.*

**Current statement**:
- in blockchain world, we have been attuned to **honest-majority assumptions**, trust running as many nodes as possible is import
- outside of blockchains, things operate with an **honest-minority assumption**, as long as there's one honest party

1. **Servers** - This one’s obvious and a well-known quantity.
2. **Servers with redundancy** - Add redundancy and the ability for anyone to spin up a server, and you get some decentralization but also retain the max efficiency of traditional
servers.
3. **These are maximally decentralized constructions, running peer-to-peer, but there’s no consensus** (or loose consensus)
	- run with an honest-minority assumption, and even a network with 10-100 nodes is perfectly decentralized
	- can be certain types there's one node, thx validity proofs don't need more (storage proof)
	- Stateless infra can enable a lot of features incorrectly attributed to blockchains, but without the burden of consensus
	- can have a state but not a real-time strict consensus state with strict state transitions associated with blockchains


### Why do we need stateless infra
---

**Current statement**:
- blockchains are extremely inefficient, requiring tens of thousands of time overheads over a server for the same compute
- validity proof and DAS aim to be a solution for more efficiency

**Solution**:
- zk tech can scale up to a million chains with universal synchronous composability and shared-security = million time improvement over monolithic chains, but it's not enough
- take a hybrid approach, while retaining decentralization
	- run on p2p with client running on each person's computer
	- stuff that needs to be coordinated on servers → moved to a p2p stateless infrastructure
	- struff that needs verifiability but no consensus→ run on ZK coprocessors
	- stuff that needs strict global consensus → run on zkR/validiums  

= parallelizing across multiple cores and multiple machines is much easier with stateless infra, which can lead to exponentially higher scale.

### Decentralisation of Stateless infra vs Blockchain
---

**Blockchain**:
- need to achieve strict global consensus (difficult process) + expensive Sybil resistance mechanism with honest-majority assumptions
- block production mechanism is at best a plutocracy (proof-of-stake) and at worst a corporatocracy (proof-of-work) → mitigate by node running but still operate with honest-majority assumptions + need thousands of nodes to achieve any level of resilience for the consensus-forming process

**Stateless Infra**:
- most of them will be fine with honest-minority assumptions → as long as there's one node, it's all fine
- they can be much more decentralizeds with much fewer nodes + fewer points of failure and centralization
= In short, if strict global consensus is not required, peer-to-peer stateless infra is both more efficient and more decentralized than blockchains.

---

## Relation between social networks and their third-parties

Source [Social networks are getting stingy with their data, leaving third-party developers in the lurch](https://techcrunch.com/2024/02/09/social-network-api-apps-twitter-reddit-threads-mastodon-bluesky/) from [Ivan Mehta](https://twitter.com/indianidle)

**Prev statement** - open network
- compagies enable third-party access to those APIs and enable them to build on top of these platforms, offering a new experience leverage by that platform

**Current statement** - restricted social network
- big companies decide to change their terms to shut out third-party exp on top of these platforms (Twitter, Redit...)
	- why: social networks realized that they were sitting on massive troves of data
- shuttered free access to its API and raised prices for other tiers = platform monetize their data of their social networks
	- limited experience, high pricing
- social networks want to protect their data from AI

**Potential future statement** - new wave of social networks
- support third-party app, no real restrictions apart from rate limiting and pagination (prevent abuse of the API)
- provide same tools and APIs to third-party devs as the ones they use to build their official apps
- this new wave is also powered by big companies; their positions as side- parties are not always clear, and that can reserve surprise in the future

---

**Personal comment**:

On the other side, with a decentralized social network like [Farcaster](https://www.farcaster.xyz/), we see full support for new clients and third-parties to build on top of the network. [Zora](https://zora.co/) is also a good example of an open network ([hyperstructure](https://jacob.energy/hyperstructures.html)) that supports third parties to leverage a new experience around the base protocol.