---
title: "Estimating Testing"
date: 2023-06-07
categories : ["testing"]
layout: post
draft: false
---

Whilst we’d love to be in a world without deadlines, pesky capitalism means not only needing to have external commitments and deadlines, but also internal planning and commitments to each other to complete work in a timely fashion, often with goalposts. They’re not deadlines, but they’re expectations.

When planning a piece of work, we might want to know the rough time it would take to get from the end of planning into users hands.

Speaking somewhat as a outsider, estimating the implementation is “easy”. The mechanics of the design have just been discussed and decided. Given prior experience with the codebase and their specialist knowledge, plus knowledge of recent issues or refactors or other risks in that area, and given some assumptions on dependencies being available, they can estimate roughly how long it might take someone of suitable skill to implement the feature as described.

Estimating testing is hard during the planning phase. Testing is the activity of offsetting important risks (often by their severity or their likelihood) through exploration. The risks are sourced from considerations, including this (obviously incomplete) list:

* What’s “near” the change that could be inadvertently affected
  * Size of change
    * How much has changed
    * Classes in users affected
    * Number of ways the change can be accessed
* Confidence of the change (is this a boring change, where we’ve done similar before, or are we breaking new ground?)
* Implementation detail
  * Unexpected changes to the plan that occurred during implementation
  * Developer info on risks
  * Unit test coverage
  * E2E test coverage
* Peer Testing outputs
* Prior experience in this functional area
  * How long since it was last tested?
  * Is it considered stable functionality? Or expected to have undocumented behaviours and undiscovered bugs?
* Experience whilst testing (e.g. unusual behaviours that merit further digging)

Some of this can be known at the Planning stage, but much of the information can’t exist yet. And even once you’ve got this information, there’s some ancillary costs we still haven’t accounted for:

* Time for conversations before and during testing to get this information
* The mechanics of testing, like setup, which can only be understood once you’ve got all of the information, and can still change during the course of testing
* The administration overhead of testing (bug reports, for example, which can’t be known or counted before testing)

Once the information is available (most of which might be available as testing begins) the estimate would still only account for the “first pass” of testing. Any issues encountered during testing add a cost for investigating and reporting, plus the inevitable fix/retest cycle, which have all the same considerations again.

> All models are wrong, some are useful. — George Box

We can give estimates, absolutely, but knowing the tremendous gaps should inform how seriously you should take them, and the importance of a decision you should be willing to make when using them.
