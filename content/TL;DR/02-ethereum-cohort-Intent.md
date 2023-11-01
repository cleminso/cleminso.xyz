---
type: post
title: "02 - Ethereum Cohort - Intent"
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
date: {}
cover:
  image: <image path/url>
  alt: <alt text>
  caption: <text>
  relative: false
  hidden: true
---

In this post, I provide an Introduction about Intent and their risks. I will abstract the requirements for the Intent Infrastructure.

Ressources used: [Lagrangian Intent research](https://blog.20squares.xyz//lagrangian-intent-search-i/) 

## Introduction

Today, we have to way to interact with a Blockchain:

1. by centralized exchange: we delegate the control of our keys and fund to a third parties. That provides a better UX, but we accept do not hold anything = 0 sovereignty
2. self-custody and interact ourselves with the blockchain: we keep the control of your keys and initiate our blockchain interaction ourselves. We need to love to jump into a jungle; bigger risk/scam exposition, but you keep your sovereignty

Well, Intents is between. You keep your sovereignty, but you enable “how much I accept to delegate to a third parties”.

**Benefices**:

- improve UX: third parties subsidize your gas/pay gas in different tokens
- better execution: not necessary to predefine a route when the user’s signs the message. How? because intents **get matched** and **executed** together
- more transparency by open mempool and collaborative  architecture

EVM is not built to support Intents → need to build a new Infrastructure with another mempool standard, and this time an **open mempool** (be careful is not the case for all project).

## So what’s Intents?

*Imo: Intents are not really well definite and still in production, we need additional feedback to exactly know what is look like*

The current way to define the essence of Intents if: **that represent a state changes, bringing you to your desired future state.**

### How users interact or initiate their goal?

1. **Create** their desired outcome 
2. **Propagate** it to an Intent pool, allowing discovery by solvers
3. **Matching** founded and monitored by Solvers, they specified the state transitions
4. **Execution**, Solvers submit the transactions to the blockchain to be executed and settled
5. **Validation** and **verification** by an oracle before to releasing payments

### Where is the complexity?

- need to have a system/infrastructre, capable to recognizing  the language used by user’s
- the more the language is formal, the more is difficult it is to decide the statements
    - that restricted to a specific space, EVM for example + define what’s the best path in this space
    - also that needs to be recognized  and interpreted by the system establish if a statement can or cannot be proved

⇒ that ask a good UX, user’s need to know what they exactly can ask. Also, Intent researchers have to be enabled to read and execute this new statement.

## Where is the risk?

I like this [quotation](https://twitter.com/DavideCrapis/status/1684685728360640513) from [David Crapis](https://twitter.com/DavideCrapis): *I think the limits of intent-based models are closely related to alignment: the ability to express my preference & the risk that such preference will be satisfied to an acceptable degree.*

In the way “express your goal” we need to consider how to express “what’s not my goal”.

Also, Quintus [mentions good points](https://twitter.com/0xQuintus/status/1664288412281737216) here

Closed and Permissioned intent pool: 

- bad actors have majority access to the pool → this risks centralizing the builder market
- permissioned pools require trusting the permissioned parties, and this trust is sticky
- by giving more degree of possibilities, MEV actors have more place to manipulate the pool if it is closed

The best way to understand Intents is to ask ourselves why it’s sexy or not and to read the critics about this new narrative. Many contents and documentations just add buzzwords to their articles and drown all the value and risks of Intents

Fun fact, Intent was mentioned several years ago by Google by [Web Intent](https://www.w3.org/TR/web-intents/).

