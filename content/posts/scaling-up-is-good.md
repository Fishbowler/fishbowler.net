---
title: "Scaling up is good, but the how is hard"
date: 2023-04-14
categories : ["testing"]
layout: post
draft: false
---

Inspired by the [CAST 2014 Keynote](https://www.youtube.com/watch?v=K6gIQYfXn5Q) by Trish Khoo

Trish noted that in the Old World, devs would claim they couldn’t test.

“You do it. You’re so much better at it than me.”

Like a sibling avoiding doing the vacuuming.

Trish noted the fallacy of time saving through segregation - where a person implements in isolation, hands to test, who test in isolation, who creates a bug, that is later picked up by the dev in isolation. This pattern has multiple instances of wait time, of context switching, of missing information through imperfect written word.

* Test logs a bug. Waits for dev.
* Dev opens the bug, remembers old work
* Dev waits for tester to answer clarifying question
* Dev fixes, waits for tester again
* Tester tests, nothing is different, waits for developer to confirm that this is the correct build…

Trish noted the absolute existence of Role Justifying Activities in low-trust organisations, where value-output roles like testers (rather than artifact-output roles like developers) are forced to spend time writing documents or recording information to act as an artifact proxy for their intangible value.

Trish compared the various tester personas that organisations had sought:

* Testers who push buttons, according to some script
* Testers who can explore software
* Testers who automate (and are sometimes told to do so, blindly)
* Testers who are test specialists who split their time between testing and coaching others to test
* Testers who code, who can contribute application code and take part in code reviews
* Testers who code, who create tools to improve the testing

In my work life right now, the Engineering org is considering its pain points, and how to use its "20% time". Testing needs to develop its own priorities too, about what a good use of time would be.

We would like to get to a point where we’re less reactive to Product work, and could have time to test outside of that.

* We’d like to be able to run experiments e.g. What’s the atomic performance of various API endpoints like? How do the various fields in registration and login perform when emoji are involved?
* We’d also like to run regression in the same fashion - learn about the current behaviour of an area of the system that hasn’t been looked at in some time. e.g. How does the Events section of the app work? What 3rd party integrations do we use? What event info do we hold? How is it configured? How sensitive is it to timezone? Can a user register to multiple events? Can a user register to concurrent events?

(These feel rather associated to Trish Khoo's second persona)

Guaranteeing the space to always do this might tie up all of our 20% time for a while, but it will also serve to mature our internal testing capability.

We've made some other recent progress recently. We’ve already embedded into the team that not every change requires eyes of a test specialist (related to the 4th persona?). One tester has published a Test Data sheet, showing variation in test data setups, enabling others to better test (which ties to Trish’s last persona)

I recently lamented a lack of pairing/mobbing through problems, solving that context switch, and also stands as bidirectional coaching on other disciplines. Another tester suggested that a lot of the same value might be gotten asynchronously by testers documenting their thinking and working in Slack on various matters - this would demonstrate tester thinking and skills to others, and could form a searchable repository. This feels like an extension of the 4th persona. Maybe this needs testing!
