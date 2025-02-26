---
title: "Layered Testing Cake"
date: 2025-02-26
categories : ["testing"]
layout: post
draft: false
---

About a year and a half ago, I wrote about the [desire for 100% coverage]({{< ref "coverage.md" >}}). This topic came up again recently when a release was found to contain a bug. It was before it was shipped, but it was pretty close.

And so the questions begin.

- Why didn't testing find this sooner?
- How do we make our release tests more rigorous?

The first question is absolutely the right question to be asking. The second misunderstands what testing is in a modern SDLC.

Given a bad idea or a bad piece of code, a myriad of checks exist between the developer who wrote it and the precious production system. For the sake of argument, we'll assume this is just a bug, and not an intentionally malicious contribution.

- When the developer is in their IDE, we have static analysis, making sure that what they're writing is actually intelligible code. Some IDEs go further and suggest simplifications or performance improvements as they type.
- If there's a linter, modern IDEs can run them in pseudo-realtime too, looking for unused dependencies, and potential runtime errors.
- Before they push, they probably run the existing unit tests along with any new ones they've added for their change
- If it's the kind of project that has integration tests, they might run those too
- If they're lucky enough to have end-to-end tests, there's another layer of tests that can be run
- Then, a PR is made. The CI can build the code, then has another crack at all of those lints and tests, avoiding any "Works On My Machine" style of problem. CI might have access to variations of build, test or runtime environment. If it's very fancy, maybe there are additional checks like Dynamic Analysis, or perhaps a deployment is attempted to a preview environment.
- Another human appears! A code review of the PR can spot stuff that tests can't, because they've got a few things that the codebase and the tools don't. They've got access to the intent behind the change, and a memory, both of conversations (since we know that Jira and other written mediums never contain _everything_) and of previous problems encountered by both this project, and in every other place they've ever worked. Every time you get a code review from a particular person, you're potentially getting a better and better quality of review as they continue to learn and improve. The reviewer can also look for ephemeral stuff like 'house style' which improves maintainability down the line.
- Merging the code might well run tests again, this time against the resultant new codebase, which could include other changes.
- Once code is deployed, comes testing. Depending on house processes and the tools available, this might even come before the merge. The developer has already tested their change, but getting an independent bit of exploratory testing of the change by another person, who isn't so close to the code, or to what you believed that ambiguous line meant in Jira. They can explore how the new system behaves with the change, whether it achieves the original intent, and whether it meets some expectations. They can design and enact experiments to see whether the change introduces unforeseen side effects or errors, be they functional or performance or security or something else. Moreover, placing human eyes on the running system means a lot - humans might not be great at perfectly describing what right looks like, but they're great at heuristically determining wrong at a glance.
- Later comes a release, where a set of changes are bundled together to be the next diff against the previous release. These can be tested with code and with exploratory skill again, this time looking for more combinations (like did a later change break the things that were working earlier), or looking for upgrade errors between versions, like missing assets or corrupted data.
- Deployments to successive environments (e.g. Dev, Test, Staging, Production) perhaps give access to different data sets, or different hardware profiles. Deployment tooling can have its own checks, to see if deployments and migrations succeed. Similarly the kind of tests run on different environments might differ (e.g. few folks run destructive tests in production, but performance tests on a development server might not be representative)

We don't need unit tests to be 100% effective, or exploratory testing of a feature to be 100% effective. We don't need any of these layers to be 100% effective. In fact, we can be pretty confident that none of them ever could be. An end-to-end test won't directly validate inputs and outputs of a method, and a unit test rarely performs image comparisons and has nothing to do with deployments.

Together, we want all of these checks to make up a 100% effective net for problems, combining like a Megazord to protect Angel Grove from a giant bug. We probably still don't quite reach 100% effectiveness, but from each problem that reaches production (or even each class of problem), we can learn and improve our checks, edging ever closer.

I've implied in the title that this as a layered cake, but this has a proper name. This is known as the Swiss Cheese Model of Risk. Each layer has holes, but that's okay, so long as we're aware of the capabilities and holes in our other layers, and that we respond appropriately to the problems that do get through.

![](/img/swiss_cheese_model.svg)
(Image By User:BenAveling - File:Swiss cheese model.svg, CC BY-SA 4.0, <https://commons.wikimedia.org/w/index.php?curid=133912327>)
