---
title: "From automation to learning, and back again"
date: 2020-11-04
categories : ["testing", "technology", "learning"]
layout: post
draft: false
---

In May 2019, I was sat at my desk, filling in a timesheet, wondering yet again if I'd actually done the correct number of hours. My company runs a flexible working policy, where, whilst a day is 7½ hours and there's 5 days in a regular week, that doesn't mean that you have fixed working patterns or need to stick to a fixed number of hours in a day, so long as it remains compatible with your team and you get all of your hours done eventually. We use Jira with Tempo plugin for time recording. One project per customer, plus one extra internal project to capture holiday etc., we collect data on 100% of our day. It's a consultancy, so it's a necessary evil that facilitates billing, but also helps the company with profitability and other MI like that. Tempo's reporting didn't solve a problem that I had. 

What I really wanted to know was “Since 1st Jan this year, how many hours have I worked above or below what I should have?” (or "Can I leave early today?")

You can do it per “period” (months), but we don’t care so much about that in terms of teams and individuals - if you work late on the 31st, you can finish early on the 1st - this is fine. 

Of course, I’m an engineer. The greatest thing about code - the thing I try to inspire my kids with - is that when a tool doesn’t exist, you can just make it yourself!

TempoFlex was born as a command line application. After a day or so of tinkering, authenticating securely when the credentials are stored in LastPass became unwieldy. It was suggested that I solve this by looking to port the logic to a Chrome Extension, making authentication a non-issue as it lives in the browser. By the start of June, TempoFlex was working for my purposes and published to [GitHub](https://github.com/Fishbowler/tempoflex-chrome-extension).

At this point, it became a background project that I used to learn. My strengths as an engineer lie most strongly in testing rather than developing applications, and that testing is most exercised often against applications built by others. I had an application available with a single stakeholder, and took the opportunity to expand my knowledge of implementing unit tests, and of what makes code easy & hard to test. Other blog posts can talk as to why this is a terrible idea in practice, but as a learning exercise I sought for (and reached) 100% test coverage. Initially attempted as an exercise in unit testing, that reached into rewiring of private vs public methods, but then reworked as integration tests. After that, test fixtures were rewritten for readability and to reduce repetition. All highly rewarding.

Over the course of this journey, I’d enlisted the help of others at work to test changes and assist in solving some of the more intractable problems. In doing so, it garnered users and in doing so, accidentally accrued stakeholders with their own individual use-cases. What happens when someone logs tomorrow’s holiday today? What happens for users who joined the company during this calendar year? The issue tracker accrued issues, those issues were resolved and additional features added, such as SAST and dependency scanning and Firefox support.

Atlassian’s recent announcements about the imminent demise of Jira Server in its current license model could, in time, spell an end to the usefulness of TempoFlex for me, or conversely create a new set of requirements for TempoFlex for an entirely differently platform. Regardless of the future of TempoFlex, I look forward to picking up other projects in the future, and continuing to develop them in the open.
