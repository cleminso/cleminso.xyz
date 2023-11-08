---
type: post
title: "TL;DR #003 - ZKP benefices"
draft: false
description: Prove something by revealing only necessary information.
weight: 997
aliases:
  - /ethereum-cohort-01
tags:
  - Ethereum
  - Zero-Knowledge Proof
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
date: {2023-10-12T10:02:06+02:00}
cover:
  image: <image path/url>
  alt: <alt text>
  caption: <text>
  relative: false
  hidden: true
---

**What I want to explain on this blog post?**

I want to explain why zkp are useful with a product view. Showing some examples. I will abstract to explain how zkp works.
And open on some social benefices.

Currently, if we want to prove x is true, we need to **reveal** some information about why x is true by showing how is happened and convince the audience.
With Zero Knowledge Proof, we can convince a statement/fact is true **without revealing** any additional information, about how is happened.
The magic of ZK proofs is that they are “proofs” in the mathematical sense of the word: all true statements can be proved, and only true statements can be proved.

## Summary:

ZKP allows a prover to prove to a verifier x statement is true, without revealing any other information.
- The verifier only sees the fact proving the statement x is true. → It's the Zero-Knowledge proprieties
- If the statement x is true, an honest verifier will be convinced of this fact by an honest prover → Completeness proprieties
- If the statement x is false, no corrupt prover can convince an honest verifier this statement x is true. Except some probability, depends on the types of proof are used. zk-SNARK required a trusted set-up and that can happened, currently, zk-STARK does have that. → Soundness proprieties

*Computational Integrity: doing the right computation, even when no one is watching* [source](https://www.crowdcast.io/e/computational-integrity/register).

## What are good product properties of ZKP? What could it be used in?

- Privacy preserving: prove x statements about data without revealing all actual data.
- Trustlessness: enables trustless verifications of statements without relying on a trusted third party.
- Digital credentials: proof of who you're without revealing your identity
- Computational integrity: guarantee the code and data can't be tampered

## Product is about how can we solve people's problems in a way that benefits the ecosystem?

- Authentication and ownership:
	- Are you xxx without revealing your name? 
	- Do you hold x NFT to attend at this private party, without revealing your address and NFT id?
- Proof that something verifiably happened:
	- about your identity: name, date of birth
	- about a payment: I send you your salary at this date. I sent my rent before x date
- Certifications of trust:
	1. I made a transfer via Tornado Cash
	2. I uploaded a proof that my wallet is not part of the OFAC list
	3. I get my money out anonymously
- Accelerate administrative procedures:
	- Someone wants to acquire a new business. Currently, is fastidious works and can be tampered. With zkp ask whatever you need to know about this business, like solvability financial; last trimester benefices… The business in question can provide you a proof for each request without revealing any important informations

### Why you should implement zkp to your product?

- **Enhance the security** of your system. Mix with encryption, zkp provides a safe place for your user's. With zkp any data is revealed, and with encryption, the team don't hold any information about the user's data => safe place
- **Assure** and **maintain** user's data private when they interact with your product
- Enable your user's to **prover their ID** when they want to auth at your product

### What's the frictions points for a general democratization?

- Complexity: making them more accessible for a general audience, and developing user-friendly interfaces and experience
- Performances: it's expensive, and it's required to make proof system more efficient and faster
- Trust and adoption: by democratize how it's works and can be used, that improves the trust towards these new technologies
Convincing individuals and organizations to adopt ZKPs, especially in industries where trust is paramount (e.g., finance or healthcare), can be difficult. Building trust and demonstrating the benefits of ZKPs are essential.

### What's the human benefices?

- Keep some information privates and show only what is needed
- Stop trusting, simply prove and verify
- Encourage honest behavior
- Verifying facts, proving the authenticity and trustworthiness of information become critical

### What's can be human downward slide/derive?

- Potentially social exclusion of people, improvement of dispatch social classes

---

Adopt new technologies can be difficult at different layers (developers, users, organization). Build a trust and highlighting the benefits of ZKPs are important things to contribute to the democratization.