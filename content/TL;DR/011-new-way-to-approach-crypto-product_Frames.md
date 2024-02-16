---
title: 'TL;DR #011 - New way to approach crypto product, Frames'
date: 2024-02-07T00:00:00
weight: 989
draft: false
aliases: 
  - /tldr/011/ 
description: In this TL;DR, discover a new way way to build crypto product and what is Farcaster Frame.
Params:
  - ShowBreadCrumbs: true
  - ShowPostNavLinks: true
tags:
  - Product
  - Web3 Thoughts
  - Protocol
image: 
---

## On Crypto

Source [On Crypto](https://gestalt.cafe/on-crypto/) essay by [Arnaud Schenk](https://twitter.com/_arnauds_)

In this essay, Arnaud explains how we approached crypto in the past and how we can progress now towards tools for conspiracy ideology.

Crypto space can be summarized into two unaligned baheviors:
- early believers, mostly drive by cypherpunk ideology 
- mindless and speculative, mostly drive by the gain and care about the good health of the crypto space

→ Rethink the way to build?

1. Being more solution-oriented than problem-oriented
= find the shortest path that fixes an identified problem for an identified user

2. Being product-focused, aim towards the following startup model: trying to find something with high scalability, low capex, ongoing opex, easy to use with minimal friction

But crypto hold sway over their values, don't naturally mach with this approach.  
Crypto imposes:
- heavy costs
- identified problem which fits the above exceptions, rarely going to though the decentralize and make it trustless
- ideological costs, maximize transparence, democratize in decision making, avoid "rent seeking"

=> hard to combinate problems look like startup, and filter them through the above ideological and technical constraints 

→ Lessons from the past

- early day industry happened with a small group of people who just found the idea neat and exciting
figured out how to make it work only because they felt the answer to “wouldn’t it be neat…?” was straightforwardly “yes”.
- last year's effort and energy were spent trying to come up with justifications for crypto's existence, which assuaged these outsiders concerns.

-> Ideological baggage

**Activism** - aims to be public and open
- It wants to recruit people to its cause and influence them through membership numbers
- Its goals are legible and visible to all, and they need to be made agreeable to those involved

**Conspiracy** - aims to be private and largely closed
- Its existence and goals may never be known outside of the group

Crypto, as the brainchild of the Cypherpunks, is a technology oriented towards activism, with an emphasis on openness, transparency, democratic decision-making, and equality of power as values.

*But to succeed, move towards the Conspiracy end of the axis and do things that don't scale is the 'best way'*

→ Tools for Conspiracy

Ideological beliefs was necessary to start and legitimate crypto across the world. Now these are restraining us.

Crypto recognizes the trust problem on the Internet, and most of our institutions cannot sustain it.

The blockchain approach is:
- build a new **trustless system**
- 'if you can observe everything, including all the immutable rules that you will subject yourself to as well as what everyone else is doing, you can independently verify you won’t get screwed'


Arnaud thinks 'the idea that trustlessness implies ineffectiveness' and we should:
- build tools and technology that help establish trust. towards building tools for conspiracy
- give small groups the ability to find each other, acquire resources, coordinate, and act without needing the approval of others or making their existence known

> Give people a neutral tool to enable them to pursue their own goals without having to ask for anyone's permission or involving anyone they don't want to involve.

---

I really like the last sentence: give tools to enable everyone to pursue their own goals. We can see it with the [Farcaster Protocol](https://twitter.com/farcaster_xyz), which enables builders to develop their app and create on top of it, taking advantage of the social network effect.

That is what we aim to develop with [0ptima](https://cleminso.xyz/product-review/009-0ptima/): enable people to create their own economy based on privacy rights.

---

## Frames

Source [How to think about Frames](https://medium.com/@decktonic/how-to-think-about-frames-07853d93a549) by [Christian Montoya](https://twitter.com/MidwitMilhouse).

### What is a Frame?

- Is embedded media
    - the media are not interactive or embedded webpages; they result from buttons
    - but the frame itself is interactive
- Is like open graph tags but with buttons underneath that enable users to interact with the embedded media.
- Frame acts more like a traditional web app
    - that don't use wallets or connector services

### How is work?
1. the user clicks on the buttons
2. the post request is sent with a signed payload to the IRL provided in the Frame
3. that URL responds with another Frame
4. the signed payload includes which button was pressed and a cryptographic hash that can be used to reliably identify the user who submitted it
    - important because it means you can filter out bots from interacting with the Frame, or hitting the endpoint

With Frames, however, you can decode the signed payload and find the ID of the user that submitted the request for any action that you want to limit to real users.

### Sponsored actions

Transactions are possible, sponsored, and facilitated by the server

1. dev created an NFT contract and put up funds ahead of time to cover the cost of each mint
2. users click mint btn, the server finds the connected address for that user and mint the NFT with the dev wallet to the user's address
	- there is a tx but the user isn't doing the tx, and doesn't pay for it

---

I'm impatient to see more Frame experiences, whether basic or funny. That has the potential to simplify actions and improve UX at several levels, powered by an open protocol, Farcaster.