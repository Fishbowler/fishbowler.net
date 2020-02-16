---
title: "The Value of Automation"
date: 2020-02-16
categories : ["testing", "technology"]
layout: post
draft: true
---

I've been asked many times to discuss test automation and its value to my team.

I've promoted a team's efforts to plug the gaps in UI tests of critical paths, or defended a woeful lack of effort on mobile apps, or pushed back against UI tests to extend the middle slice of our pyramid. With a CTO this is often a conversation about how we focus or improve or prioritise existing tester efforts and what our test recruitment priorities should be. With another tester, this conversation can be about projects and risk and value, or maybe about showing how to prove testing's ROI on paper.

In many conversations, the topic of hiring an automation specialist comes up. In any conversation where I've got influence, I've said the same thing: no chance.

It's not that I don't value the skills. I absolutely do. I wouldn't be ploughing effort into automation if I didn't. I have skills in this myself. I automate. I coach on automation at work. I teach automation at NottsTest occasionally too. I think automation is a valuable tool.

_If you're in the area you should come along to [NottsTest](https://www.meetup.com/ministry-of-testing-nottingham/) - we're very friendly and our sponsors, [Rebel](https://rebelrecruiters.co.uk/), are lush - you won't get a sales pitch, but there's job help available if you want it. Talks cater for soft and technical skills, and for all levels of experience. Tap me up on Twitter if you wanna know more._

It's not that I'm loathe to hire specialists either. So far it hasn't come up, but I don't think I'd be against hiring a performance or security or usability or accessibility specialist. So whilst I've got no empirical proof, I don't think it's the concept of specialists that I have a problem with.

I think my objection stems from the majority of test automation specialists I've spoken to. I'm talking about regular agency-sourced Selenium-for-hire automation people. Almost every one I've spoken to seems to leave me with two common impressions:

* They think they're one stage more advanced in their career than a tester without these skills
* I think their actual skills in testing are _worse_ than a general practitioner of testing

The first stems from a common trajectory that many testers (myself included) see themselves on at some point, likely early in their career:

{{< blockquote >}}To win at testing, and earn all of the moneys, I need to be good at UI automation.{{< /blockquote >}}

What a complete crock. I've worked hard to dispel this in every arena I can. For instance, a few years ago, I worked at a company where our community of testers built a Core Skills list by which to judge ourselves. Of the 22 skills we came up with, less than a quarter were technical, only two regarded automation, whilst another two were on the topic of HTTP operations. Most were soft skills. "Asking questions" and "Using heuristics" appeared much higher on the list in every way - it's literally higher on the list, was suggested earlier chronologically, and was regarded as generally more important and more applicable to everyday testing.

The second thought stems from me listening to how these people work. They're automation focussed. They wish to spend 100% of their time on automation. "Give me a list of things and I can automate them all". Not enough thought goes into value of _this_ particular test, whether their Selenium framework is the correct level of the pyramid to be automating at, or whether this should be automated at all. My overall impression of these specialists is that they relied so much on other people for "the list of things" and struggled to conjure said list themselves.

Don't get me wrong, I sometimes write code to help my testing, and some of that uses tools like Selenium or otherwise drives a browser. These tools aren't always needed, but when they are, they can provide ongoing value for my team in return for an investment from me. I'd also say I really enjoy it when I'm doing it - I totally understand why developers want to be developers. Writing code that can drive a browser isn't a strong technical skill though (heuristic: if I can do it...), especially so for all those developers around me who already write really impressive code all day AND already know how to write good unit tests. The gap isn't so big. But does your team have strong expertise in testing database logic, or identifying performance bottlenecks, or threat modelling your intended architecture and making the appropriate mitigations? If not, maybe another person who's a worse coder than your developers and a worse tester than your testers isn't the right business decision.

_I apologise to anyone who's read this and is offended because they believe my description applies to them. It probably doesn't. You're reading a blog post, seeking out alternative points of view, and are already capable of analysing a situation through other lenses. You're probably a fine tester, and you can choose to do something else if everyone starts to think as I do - that there really isn't much call for a "Test Automation Engineer" in a modern team._
