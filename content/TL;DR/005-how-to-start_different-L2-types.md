---
title: 'TL;DR #005 - How to start; Different L2 types'
date: 2023-11-15T10:02:06+02:00
weight: 995
draft: false
tags:
  - General Knowledge
  - Layer 2
  - Ethereum
ShowBreadCrumbs: true
---

## Start with why?

[Source](https://www.youtube.com/watch?v=u4ZoJKF_VuA) from [Simon Sinek](https://twitter.com/simonsinek)

*I found this video very valuable for providing a simple framework to set up the basics for a new initiative.*

*I start all of my product initiatives, and that helps me to write and communicate a logical flow to the stakeholders.*

*That provides a self-introspection to define and explore our core motivations.* 

**Why we do it?** = problem statement
- what's your cause / purpose / belief 
<!-- find a definition for each word cause/purpose/belief -->
- why your organization exist?

**How we do it?** = user story (process, behavior)

- limbic brains → handles all your feelings, like trust and loyalty, humain behavior, decision making but not capacity for language

**What we do?** = we produce the what, to achieve the how based on the why.

Aka the final product with the user flow.

What → How => people can understand vast amounts of complicated information features, benefits, fact and figures

Why → How → What => talking directly to the part of the brain that controls behavior, allowing people to rationalize it with tangible things we say and do

--> *The success of business communication is like*:

Example if Apple were using a lambda marketing:

- what? we make great computers

- How? they're beautifully designed, simple to use, and user-friendly. 

=> Do you wanna buy one? 

Apple's current communication:

- why? in everything we do, we believe in challenging the status quo. We believe in thinking differently

- how? the way to challenge the status quo is by making our products beautifully designed, simple to use, and user-friendly

- what? we just happen to make great computers

=> Do you wanna buy one?

People don't buy what you do; **they buy why you do it**

The goal is not to do business with everybody who needs what you have

The goal is to do business with people who believe what you believe

---

## Different types of L2s from Vitalik.B
[Source](https://vitalik.eth.limo/general/2023/10/31/l2types.html)

Layer 2 ecosystem has been expanding this year, with new initiatives like:
- [L2beat page](https://l2beat.com/scaling/summary) - summarizing the state of each project
- Layer 1 projects move toward being Rollup or Validium
- Broader efforts are around EVM

Layer 2 trend:
- independent L1 are seeking to come closer to the Ethereum ecosystem by developing their Rollup initiative.
	- step-by-step transition to minimize the risks
- centralized project starts to care more about user security
	- only need a intermediate level of decentralization
	- **very high level of throughput**
- non-financial app, wants to be decentralized
	- they need a intermediate level of security
=> Users from the non-blockchain world will not be paying the current transaction costs.

Two key dimensions to come closer to Ethereum
- security of **withdrawing** to Ethereum
- security of **reading** Ethereum

### Rollups vs Validiums vs Disconnected systems

→ What are the technology tradeoffs or levels of guarantee users have to be able to take the asset back to L1?

With **Rollup** - computation proven via fraud/zk-proof + data stored on L1

- You can always bring the asset back to L1

With **Validiums** - computation proven by zk-SNARKs + data stored off-chain

- Data availability failures can cause assets to be lost but not stolen

With **Disconnected systems** - a separate chain or server

- Trust one or a small group of people not to steal your funds or lose the keys

### What motivates applications to choose 
a particular point on that spectrum, and not some point further left or further right?

{{< figure src="/img/rollup_vs_validium.png" title="" >}}

- native DA cost of Ethereum
- different degrees of applications need to satisfied their users
- the ability to read the Ethereum blockchain, in case of problem
    - being able to revert if Ethereum reverts

### Does having a bridge make you a validium?

Currently, not yet, because:

Scenario 1: top chain + bridge contract accept block header (check the Ethereum consensus)

In this scenario, not yet:

- is only a validation of signed blocks and not a validation of the state transitions are correct
- the top chain has no way to read Ethereum

Scenario 2: validating bridge checks the consensus + proving the state of any block are computed correctly with a zk-SNARKs

- the top chain can't steal users funds
- can publish block with unavailable data
- preventing everyone from withdrawing
- cannot read Ethereum
So the answer is, not yet.
(same security model as a validium)

To allow the top chain to read Ethereum, we need:
- put a bridge contract validating Ethereum blocks **inside the top chain**
- each block in the top chain **contains a hash** of a recent Ethereum block + fork choice rule to enforce the hash likings

--- 

