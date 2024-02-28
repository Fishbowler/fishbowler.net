---
title: "QE Babble - Speed vs Quality (21 Feb 2024)"
date: 2024-02-27
categories : ["testing"]
layout: post
draft: false
---

In my third week working at Doccla, the testers (Rachel and I) tuned into a session of QE Babble (available on [LinkedIn](https://www.linkedin.com/company/qebabble/) and [Meetup](https://www.meetup.com/qababble-online/), although the latter links back to the former), hoping to get answers to one of the industry’s most pressing problems. The panel were asked a number of questions, and gave answers in turn. Whilst naturally, nobody had a silver bullet, there were some general themes that we liked. Here’s a few choice quotes I picked out, and a summary of the conversation me and Rachel had in our debrief (enhanced with poetic license, as if I’d been eloquent rather than waffly and hand-wavey).

{{< blockquote >}}
“Risks in the business”
{{< /blockquote >}}

There are more risks that just ‘software that doesn’t work'. At Doccla, we have clinical regulation, contractual obligation, new business challenges, competition threats and a host of other risks. Even when the result is ‘broken software’ that might mean something more to someone else, like their health. As testers we can never test everything, and so we prioritise. We do that based on risks, and we can do that best when we’ve got all of the information.

 {{< blockquote >}}
“Risks vs Impact”
{{< /blockquote >}}

Since we can’t test everything, we balance risk against the impact if the risk were realised. We test the things that are likely to go wrong, and the things that would be really really bad if they did go wrong. Here’s the picture version:

![Hand-drawn chart of risk against impact, with a line joining the ends of the x and y axis. Anything high on either axis is tested, and anything low on either axis doesn't require testing](/img/risk-v-impact.png)

{{< blockquote >}}
“Getting people excited about testing”
{{< /blockquote >}}

Software quality isn’t a thing a bunch of testers add in the end via bug reports. We want everyone involved in testing, and not just because delivering quality is part of their job, but because they like it and want it. Getting people excited about a thing that isn’t the primary concern of their role isn’t an easy thing, especially when even if you could, people aren’t exactly free to just pursue their whims during the workday.

{{< blockquote >}}
"Some things are always going to be missed, but we always go back and learn about it"
{{< /blockquote >}}

We’re not going to have bug-free software. With infinite possible tests, and risks known and unknown, even with enormous resources we wouldn’t find everything before it hits production. What’s important is that when it happens, it only happens once. We work out what we didn’t know or misunderstood, and so didn’t do or didn’t complete or did wrong. We make sure that next time, we don’t make that mistake again.

{{< blockquote >}}
“… getting pressure to rush testing in order to release”
{{< /blockquote >}}

Every tester at some point has had a project manager breathing down their neck, wanting testing to complete so that a delivery date can be met. They want the testing to happen quickly, to be completed properly and to find no problems. Because testers are lazy, disinterested in the business, and invent bugs to make life harder for other folk, right? Teams win and lose together. One part of a delivery team pressuring another part of the same team to do a worse job might be the worst anti-pattern I can think of.

{{< blockquote >}}
“Developers contributing to E2E tests”
{{< /blockquote >}}

Maybe this lives with being excited about testing, but even if it doesn’t, it just makes sense. The alternative is creating a bottleneck in the test team that further delays releases that could only be relieved by hiring folk to perform this specific task, which is historically difficult.

{{< blockquote >}}
“Testers can talk about regression testing at the refinement”
{{< /blockquote >}}

A great idea, especially in the context of the early stages of an E2E project, where the likelihood is that “there is no current coverage”, which in the short term is an expensive thing to tack onto every piece of work, and so might not always be appropriate. But flagging it and discussing it and tackling it is absolutely the right thing to do.

{{< blockquote >}}
“Thinking about efficiencies, testers can improve time to release with realtime collaboration”
{{< /blockquote >}}

It’s obvious. When we encounter problems, having a discussion and collaborating in a call is far more effective and time-efficient that collating evidence, logging a bug, awaiting triage and refinement and prioritisation, all the while everyone loses the context of the problem whilst they move to other things. Sure, sometimes, that collaboration will be the collation of that evidence, followed by “nah, this isn’t important, chuck it on the backlog”.

{{< blockquote >}}
“Quality is a culture. Communication and collaboration are just a part of that.”
{{< /blockquote >}}

Mic drop.
