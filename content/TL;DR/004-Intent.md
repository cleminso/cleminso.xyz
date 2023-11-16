---
type: post
title: "TL;DR #004 - Intent"
draft: false
description: Fully express your goal but at which price?
weight: 996
aliases:
  - /ethereum-cohort-01
tags:
  - Intent Infrastructure
  - Ethereum Cohort
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
date: 2023-11-01T10:02:06+02:00
cover:
  image: <image path/url>
  alt: <alt text>
  caption: <text>
  relative: false
  hidden: true
---

In this post, I will only provide an introduction to Intent and its risks.

Resources used: [Lagrangian Intent Research](https://blog.20squares.xyz//lagrangian-intent-search-i/)

## Introduction

Today, we have two ways to interact with a Blockchain:

1. By using a centralized exchange, we delegate the control of our keys and funds to third parties. This provides a better user experience, but we do not retain any sovereignty.
2. Self-custody and self-interaction with the blockchain: We maintain control of our keys and initiate our blockchain interactions. We must be prepared to navigate a jungle, which entails higher risks of scams, but it also allows us to retain our sovereignty.

Well, Intents are in between. You keep your sovereignty, but you enable “how much I accept to delegate to third parties”.

**Benefits**:

-  Improve UX: Third parties subsidize your gas/pay gas in different tokens.
- Better execution: No need to predefine a route when the user signs the message. Why? Because intents **get matched** and **executed** together.
- More transparency through an open mempool and collaborative architecture.

The EVM is not built to support Intents. We need to create a new infrastructure with a different mempool standard, and this time it's an **open mempool** (but be careful, as this is not the case for all projects).

## So, what are Intents?

*Imo, Intents are not well-defined yet and are still in production. We need additional feedback to precisely understand what they look like.*

The current way to define the essence of Intents is **that they represent state changes, bringing you to your desired future state**.

### How do users interact or initiate their goals?

1. **Create** their desired outcome 
2. **Propagate** it to an Intent pool, allowing discovery by solvers
3. **Matching** is founded and monitored by Solvers, they specified the state transitions
4. **Execution**, Solvers submit the transactions to the blockchain to be executed and settled
5. **Validation** and **verification** by an oracle before releasing payments

### Where does the complexity lie?

- need to have a system/infrastructre, capable of recognizing the language used by user’s
- the more the language is formal. The more formal the language, the more difficult it is to determine the statements.
    - It's restricted to a specific space, such as EVM, and defining the best path within this space is essential.
    - Additionally, it needs to be recognized and interpreted by the system to establish if a statement can or cannot be proved.

⇒ This requires a good UX; users have to know what they can exactly ask. Furthermore, Intent researchers must be enabled to read and execute this new statement.

## Where are the risks?

I like this [quotation](https://twitter.com/DavideCrapis/status/1684685728360640513) from [David Crapis](https://twitter.com/DavideCrapis): *I think the limits of intent-based models are closely related to alignment: the ability to express my preference & the risk that such preference will be satisfied to an acceptable degree.*

In the way 'express your goal', we need to consider how to express 'what's not my goal'.

Also, Quintus [makes valuable points here](https://twitter.com/0xQuintus/status/1664288412281737216) here

 Closed and Permissioned Intent Pool: 

- In a closed and permissioned intent pool, bad actors can gain majority access to the pool, risking centralizing the builder market.
- Permissioned pools require trusting the permissioned parties, and this trust is difficult to change.
- By providing a greater degree of possibility, MEV actors have more opportunities to manipulate the pool if it is closed.

The best way to understand Intents is to ask ourselves whether they are appealing, and to read the criticisms to this new narrative. Many pieces of content and documentation simply incorporate buzzwords into their articles, obscuring the true value and risks of Intents.

Fun fact: Google introduced the concept of [Web Intent](https://www.w3.org/TR/web-intents/) several years ago.

