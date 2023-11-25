---
title: 'TL;DR #006 - UX Flow; Build in public; Product story '
date: 2023-11-24T10:02:06
weight: 994
draft: false
Params:
  - ShowBreadCrumbs: true
  - ShowPostNavLinks: true
tags:
  - UX
  - Product Story
  - General Knowledge
---

This weekly TL;DR is fully oriented to UX product and a case studies of failed product, called Pebble.

## UX is not a flows

In this article, Pavel.P questioning and put a new prespective to see flows.

Source: [UX Is Not Flows](https://hackernoon.com/ux-is-not-flows-a6hh3wf6) by [Pavel Pekanov](https://twitter.com/pavelpekanov?ref=hackernoon)

"*Stop to looking UX from a perspective of minimizing the number of steps, pages and clicks*"
→ what exactly makes an "experience".

| Interactions → Flow → Experience

**Interactions** - action/reaction
- User does an actions (input), then the platform does something with that (output)
- A sequence of interactions creates a flow.

**Flow** - start at a point A and getting to point B 
- setting a new account is a series of micro-flow
	- entering first and last name; email; password
Interactions >2 are a flow

**Experiences** - the end-goal

"**Product UX is the sum of such experiences. Product User Experience is the sum of every tiny experience a user comes across while interacting with the Product.**"

What is the Experience we're after?

| Interactions → Flow - end users goals → end-goal is a journey - Experience

---

## Build in public

Source: [Case Study#2: Wise: Secrets of 'Building in public'](https://productify.substack.com/p/wise-secrets-of-building-in-public) by [Bandan Jot Singh](https://twitter.com/bandanjot)

Discover the new way for copagnies to develop their product with Wise as case study!  

- How important is the idea or the business model for the success of the company? Should it be protected?
- What is the single most important factor that makes a company successful? 

1. Timing
2. Team/Execution
    -  Great people and execution can triumph over another company working on the same idea but with a poorer team and execution.
3. Idea: 'Truth' Outlier
4. Business Model
5. Funding

Find the complete answer in [his TED talk](https://www.ted.com/talks/bill_gross_the_single_biggest_reason_why_start_ups_succeed?language=en#t-216239) by [Bill Gross](https://en.wikipedia.org/wiki/Bill_H._Gross)

Case study: [Wise](https://twitter.com/Wise/status/1403325880496230405) stands out compared to other companies:

- launched their first public roadmap and used this opportunity to get feedback from users on the roadmap
	1. action: build a roadmap and publish it
	2. goal: received feedback from users
	3. execution: listen to users; categorize and execute feedback
- publish their product team structure and regional focus areas
- organize Mission Days
	- this event invites users to collect ideas and shape their future roadmap

**Why are companies built in public?**
- to earn the trust of their users
- give a transparency
- allows teams to receive direct feedback from their users
- **Build an idea funnel**
	- users give feedback on what they like about the roadmap and what they don't
	- company pov: that provide an idea flow and

**Lessons for Product Managers**
- Customer trust is a big factor that can determine the success or failure of your company.
- Building in public is a great tool to get more ideas from your customers.
- Your ability to execute is more important than your ideas or business model.

---

## Failure product with Pebble

Source: [From T2 to Pebble: The Rise, Challenges, and Lessons of Building a Twitter Alternative](https://medium.com/gabor/from-t2-to-pebble-the-rise-challenges-and-lessons-of-building-a-twitter-alternative-553652f1d1e7) by [Gabor Cselle](https://twitter.com/gabor)

Congrats to Gabor.C for this introspection about his experience as a product founder!

**Context**
- after Elon Musk took over Twitter and bought half of the company, we tried to build a Twitter alternative from 0
- rapidly raised money from angels: $1.4M
- fast growth but insufficient to raise more venture capital, and tracting started shrinking before raising more
=> Shut down the project after ~10 months
For more precision, T2 was the first name before being renamed Pebble.

About the team:
- [Gabor Cselle](https://twitter.com/gabor) - co-founder
- The co-founder Sarah worked at Twitter. They help to redesign T2
- 2 senior ex-Twitter
- [Heath Fradkoff](https://twitter.com/heath_) - press relations manager

**The born**
- launched two weeks after the first git commit
- 6 users after the first day
- redesign the platform with a retro and whimsical vibe
=> Core message: “Twitter, but back to the roots.”
- Rebrand T2 to Pepple (sept. 2023). The goal was to find another name that wasn’t that derivative.

**Platform In numbers**
- used Posthog for metrics tracking (very good but quite expensive)
- VCs recommend at least 3k DAU in order to qualify for a seed raise
- T2 hit it for 3 days of the product's existence
	- 2 days of Handlegate. The accident in which Gabor.C sent out an email to users announcing that we’ll take back their handle. That caused users to return across every cohort we ever onboarded
	- 1 day for the rebrand announcement

{{< figure src="/img/dau-pebble.png" title="DAU chart over time, marked up with key events" >}}

**Others metrics:**
- **Week-to-week retention chart**
	- shows what $% of users that joined in a given week came back to the product N weeks later
- **Cumulatively registered accounts on the platform**
	- ~20k registered users
	- 33k people on the waitlist

**Why did the team fail?**

"The topline reason for the shutdown was that **we couldn’t figure out how to grow**."
- There were several alternatives, and they couldn't clearly articulate a differentiator between trust and safety. That is not enough to be interesting.
	- not enough interesting content on the platform for the experience to become a daily habit
- didn't prioritize building an app, then helped with retention or facilitated adding content to the platform (APIs)
- never had a growth strategy beyond the press-driven waitlist
	- the team expected that viral growth would come when they opened the waitlist, but it didn't happended

**What did the team do well?**
- **launch the product early**. Like that, the product is already visible, and you aren't just vaporware, increasing interest.
- **quick iterations with user feedback**. Listen to users, show them you care, and act in consequence.
	- early adopters want to contribute, help, and have a connection with the founders. Don't neglect this point
- not rely on press as a growth engine
- Prioritize **trust and safety**
	- moderation becomes more tractable with AI classifiers
	- misinformation is still hard to identify but can be easily flagged by users
=> Bluesky example: unseemly content got posted early on the platform, and after more proactive moderation, the idea of Bluesky as an unsafe place is still present.

**Gabor questioned**
- **Start earlier**, after leaving Google in July 2022
	- it was one of the first startup ideas he had
	- but he hesitated since I didn’t think the takeover would go this badly
- Started with a **Fully Algotithmic Timeline**
	- good feedback, but some users had expressed a very strong preference for a reverse-chron feed that gave them the feeling of full visibility.
	- "In retrospect, we should have never launched anything else." Based on the post-TikTok world, doing an algorithmic feed would be a no-brainer
- A lack of clarity about what kind of content we want to see in T2
	- firstly, focus on a single type of users

### Summaries with someone who wants to lunch on a Twitter alternative or something similar

- attract interesting content to help the daily retention
- give tools to help this retention
- had several growth strategies and did not bet on only one strategy
- be clear about what kind of content you want to see on your platform. That resume comes from your product vision, why you build your product, and for whom it is intended. After that, plan how you will execute it.
Why should people come onto your platform?
- because they can find quality or different content on other platforms.
- easy to use, open to cross-platform
