---
title: "The Iceberg of Inferred Acceptance Criteria"
date: 2022-11-25
categories : ["testing"]
layout: post
draft: false
---

When refining a ticket at Peppy (and likely lots of other places) we come up with Acceptance Criteria, deemed to be “The stuff that needs to be done in order to ship”. A piece of work must meet these criteria in order to ship.

They’re inherently incomplete. They can’t possibly list everything.

If a piece of software met the acceptance criteria, but damaged a user’s device while doing it, we wouldn’t ship it. We also wouldn’t include an Acceptance Criteria on every item that says “Must not damage a user's device”.

Acceptance Criteria are actually inverted rejection criteria. If an item doesn’t meet these criteria, then it can’t be accepted. The ones we know are those that are the ones that we define in the ticket, plus the ones that defined for all work (house style linting rules, agreed ways of working).

There are other hidden Acceptance Criteria that apply to all (or most) of the work that we do, hidden beneath the tip of the Iceberg of Inferred Acceptance Criteria…

[![Illustration of the Iceberg of Inferred Acceptance Criteria](/img/iceberg.png)](/img/iceberg.png)
*(click for bigger)*
