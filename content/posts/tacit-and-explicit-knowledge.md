---
title: "Tacit & Explicit Knowledge"
date: 2023-09-04
categories : ["testing"]
layout: post
draft: false
---

Dual Process Theory says that our brains work in two ways, often in parallel. One is reasoned and methodical, creating and executing on plans, analysing information, etc. The other is emotional, instinctual and cultural, acting on impulses, and taught to us from stimuli throughout our lives. This model maps directly to software implementation and testing. Some bugs are found by creating a set of actions and expectations, executing them and flagging when an expectation isn’t met. Others are more instinctual, or are obvious “that ain’t right” moments.

Our instinctual brain processes and methodical brain processes are fed by Tacit and Explicit knowledge respectively. Explicit knowledge is stuff that’s written down. For software, it’s Notion, Jira, Figma and a bunch of other things that make up our written body of knowledge about the product and the feature. Tacit knowledge is stuff that exists but isn’t written down, everything from what I had for breakfast to the many ways drivers use a car’s lights beyond the Highway Code (flashing thanks, hazards for “excuse my illegal parking”, etc). In software, it’s our experience with our tools, our experience of delivering previous features, what we’ve learned from previous jobs, and from using software in the real world (e.g. we know how chat apps should behave). We can combine both to most effective at sharing and applying knowledge & expertise.

It gets murkier though. Everyone’s worked on a project where a requirement has been misunderstood which cost time or required some rework to account for it. That means that the ability to write and to interpret explicit knowledge is itself tacit knowledge 🤯

There’s a specific skill inherent to gaining tacit knowledge called Interactive Ability. This is a skill that must be enabled by a work environment, allowing people to interact to learn someone else’s context and vernacular (to understand how they write, the terms they use, and what they mean (or think they mean) when they use them) as well as building a shared vernacular.

_O/T: Shared vernacular is really interesting, and if it reaches mass adoption the new term can replace the original. Using the trigraph for a menu was 'invented' by Norm Cox in the 1980s for the Xerox Star, but the term Hamburger Menu didn't appear until around 2008. Now it'd be unusual to call it anything else._

It’s been long known that there are strong disadvantages to having a completely independent test team. They have none of the context or domain knowledge, require specific knowledge transfer in order to be even vaguely effective, and are always involved late when the bugfixes are at their most expensive. Conversely, there’s a also a disadvantage to having a highly interdependent test team - they’re subject to all of the same biases as the development team, are neutered from effective black-box testing by having in-depth knowledge, and are likely going to miss all the same things the developers did, making them only slightly more effective than not having them at all. There’s a happy medium or trade-off to be struck. This also applies to developers for reviewing pull requests, and for most other critical analysis activity.

Part of why companies value the retention of staff is for their built-up tacit knowledge. Even asking someone to document all they know is guaranteed to leave enormous gaps unfilled (which relates to a previous blog post [The Iceberg of Inferred Acceptance Criteria]({{< ref "iceberg-of-inferred-acceptance-criteria.md" >}}), where we know that, despite best efforts, we couldn’t ever list all of the ACs for a given ticket).

This post was triggered by a discussion after watching a talk by Iain McCowatt, [here](https://www.ministryoftesting.com/testbash-talks/192a29c7) (MoT Pro subscription required)
