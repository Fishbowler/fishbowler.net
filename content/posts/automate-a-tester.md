---
title: "Can you automate a tester?"
date: 2022-12-02
categories : ["testing"]
layout: post
draft: true
---

{{< blockquote >}}
This post heavily inspired, interpreted, somewhat plagiarised (badly) from James Bach’s keynote talk at CAST 2014, and mixed in with a conversation with Nastya Miskovych about what we'd just seen.
{{< /blockquote >}}

“I want to reach 100% automated testing” — *Many people in many orgs, many times*

Wanting additional confidence from your builds is good. Wanting to not waste people’s time with repetitive activity is good. Can you, though, reduce your future salary bill by replacing a tester with code and with pipelines?

“If you can express a test as a test case, complete with preconditions, inputs and expected outputs or outcomes, then you can automate it.” — *Dan, a few weeks before watching this video*

Now, that’s not wrong. But what are the arguments against it?

When a tester is performing a test, there’s a lot going on all at once:

* The risk being explored
* The specific test case or theory or idea being enacted at this moment
* The product knowledge being employed
* The person’s role and purpose on the project, and their perception of the expectations on them
* The person’s testing skills
* The person’s temperament or personality or preferences (e.g. I like tools, I don’t like people)

That means that like most people in most roles, a tester who is given the same task (a risk) a year later would approach it differently, since many of these aspects will have evolved. Similarly, two testers, given the same risk, might approach the solution in different ways. Given that they’d both likely come up with different ways of approaching the test case, are they both valid automations? Are they both needed? The regular criticisms of automations also apply here. A machine will apply the same logic every time, never vary its approach, never change based on new information, never be distracted and never vary its timings. This also means that it only checks the outputs that are specifically configured to be checked. If a button should display a message, and the message appears when the button is pressed, then ✅ (even if it's 72pt white text on a white background).

That doesn’t mean that the checks are useless, they absolute help guarantee certain outputs, prove contracts, and many other things that might be introduced through new feature or refactoring work.

The real point is that no amount of code will replace testers, any more than Github Copilot can replace developers or ChatGPT can replace writers. Test Automation is as silly a term as Developer Automation or Manager Automation. It’s a loaded term that, as well as implying something that can’t really exist, also implies that you’re replacing the human effort with a computer, when all you’re really doing is giving a human a tool. And a jolly nice tool it is too.
