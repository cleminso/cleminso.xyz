---
type: post
title: "004 - Liquity Review"
draft: false
description: Liquity the most resilient Stablecoin.
weight: 996
aliases:
  - /first
tags:
  - Stablecoin
  - DeFi
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

Our ecosystem is built upon two fundamental pillars: Stablecoins and Oracles. However, achieving true decentralization in the realm of stablecoins remains a challenging feat.

Nobody truly provides a decentralized stablecoin, for example:
- USDC and USDT are fully centralized,  subject to the authority of centralized entities
- DAI Treasury is composed of ~80% of USDC or RWAs
- GHO is back with crypto collateral, operates under the governance of AAVE, so it's subject to potential conflicts interest.

However, they do not adhere to some of the core principles of the DeFi community, notably decentralization and open-source values. 

Furthermore, the reserves of these stablecoins tend to be overcollateralized with FIAT currencies.

## Liquity Protocol

Liquity team believes in providing a decentralized stablecoin fully built on top of blockchain value and properties. 

They enable users to draw 0% interest loans against ETH. They achieve this by **establishing a stable and secure ecosystem** supported by defense mechanisms such as Stability Pools, Redemption Mechanism, and Recovery mode.

Moreover, by creating an unstoppable stablecoin, LUSD:
- governance-free → nobody controls the protocol; just verify the code
- immutable → the system can't change the rules and nobody can initiate a change
- non-custodial → no intermediaries

In other words, by creating a secure and user-friendly way to borrow stablecoins with the most decentralized token, ETH.

*So, what exactly is Liquity and what does it do?*

Liquity is a protocol that provides a LUSD Stablecoin. The protocol enables to capture value from users by depositing their ETH as a collateral in Troves.

--- 

### Liquity defense system.

In this section, I will highlight how Liquity solved the problem statement to provide a fully decentralized Stablecoin.

1. **Stability Pool**, is the place where the loans are secured
	- The source of liquidity to **repay the debt** from liquidated Troves
	- The pool contains LUSD **provided by users** (who agreed to earn rewards from them when Troves liquidation occurred)
	
For that, we can say that the protocol is secured by users. The protocol is built to delegate security to the users, and they receive the right incentives.

During a Trove liquidation:
- x LUSD corresponding to the remaining debt of the Troves is burned from the Stability Pool to repay its debt
- the entire collateral (ETH) from the Trove is transferred to the Stability Pool

2. The **Redemption Mechanism** is a mechanism to swap LUSD for ETH (face value, as if 1 LUSD = 1$). 

It's also charged with some fees. The ETH given by the redemption mechanism comes from:
- the under-collateralized Troves (in order of risk)
- User 1 does redemption with LUSD
    - that it affects a 115% collared Troves of User 2
    - User 1 “repaid” the debt of these Troves and took the collateral in this Trove

*User 1 decides, and user 2 can't do anything. So from the perspective of User 2, it's not the same as repaying a debt because they don't get to choose when it happens.*

3. **Recovery mode**, is to protect the LUSD collateralization. 

See the Total Collateral Ratio of LUSD as a large Trove composed of all individual Troves of users.
- when the Total Collateral Ratio (TCR) of the system is <150%, Recovery Mode is activated, leading to liquidation. 

All it needs to go back to a TCR >150%

- so all Troves between 110-150% are liquidated, destroying debt
- no fees to open a Trove → good incentive to open a Trove with higher collateralization to push the system at >150% => create new secured debt

This mechanism ensures the solvency of LUSD and a dissuasion mechanism to avoid behavior.

### Which Properties of Liquity are attractive?

1. They deposit their ETH to take out loans
	- free of interest, enabling you to maintain a full exposure to ETH, while receiving LUSD
	- minimum 0.5% fee required to be paid only once. The fees are added to the liquidation reserve

	- 200 LUSD (for the liquidation reserve) is added to your debt, and it is returned when you repay your debt.
	- only LUSD is accepted to repay your debt, and when you want. (Repay your debt to get back your collateral.)
2. LUSD proprieties
	- accept only decentralized collateral: aka **ETH**
	- unstoppable Stablecoin - non-custodial, immutable, and governance-free
3. Loans are paid out in LUSD (pegged to USD)
	- the loans are secured by the Stability Pool system, where users stake their LUSD
4. Maintain a Collateral Ratio
	- minimum 110% (or 150% during the recovery mode)
(If you're familiar with Liquity you know it is more complex. The Troves with the lowest collateral ratio can be liquidated same if his is >110% coll.ratio)

### Benefits from using Liquity.

1. Protect the protocol and users with the Redemption mechanism

If your Troves is liquidated, you lose your ETH collateral. But you still keep your LUSD, with that, you can redeem 1$ LUSD for 1$ ETH
    - in theory users only lose 10% of their funds

2. Stake and secure the protocol
	- deposit your LUSD to the Stability Pool
	- earn liquidation gains and LQTY rewards
	- stake LQTY and earn revenue from insurance fees in LUSD and redemption fees in ETH

3. All fees take by the protocol are to secure the protocol or give it to the users
	- initial fees when you open a troves. Minimum 0.50% fees, added to the Liquidation Reserve
	- variable fees (determined algorithmic) are taken during the Redemption mechenism
	- Liquidity Pool stakers, receive fees during Troves Liquidation

=> Fees are redistributed to Stability pool and LQTY Stakers

--- 

Furthermore, Liquity's commitment to decentralized collateralization and the provision of an unstoppable Stablecoin showcases its dedication to the core values of DeFi.

In my next review, I will discuss DeFi Pooling and how liquity is deployed on Starknet.

--- 

Sources used:

https://docs.liquity.org/

[Marathon DeFi TokenBrice #12 - Liquity & Chicken Bonds (2/4)
](https://www.youtube.com/watch?v=IDAqnCXcAXU)
