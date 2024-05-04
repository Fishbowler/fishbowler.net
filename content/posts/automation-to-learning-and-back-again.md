---
title: "That time I wanted 100% test coverage"
date: 2024-05-04
categories : ["testing", "technology", "learning"]
layout: post
draft: false
---

In May 2019, filling in a timesheet, I was wondering if I'd actually done the correct number of hours. My company was a consultancy, so all hours needed to be recorded. It also ran a flexible working policy, so you didn't fixed working patterns or a fixed number of hours in a day, so long as it remains compatible with your team and you get all of your hours done eventually. We used Tempo (a Jira plugin) for time recording. One project per customer (plus one for internal stuff like holidays and company meetings) so we collect data on 100% of our day.

What I really wanted to know was "Can I leave early today?", which equated to something like “Since 1st Jan this year, how many hours have I worked above or below what I should have?” - Tempo was great for company MI like profitability, but couldn't solve this question for me.

Of course, I’m an engineer. The greatest thing about code (and something I try to inspire my kids with) is that when a tool doesn’t exist, you can just make it yourself!

TempoFlex was born as a command line application, but authenticating with Jira when the credentials were in LastPass became unwieldy. A friend suggested that I look to port the logic to a Chrome Extension, making authentication a non-issue, since it lives in the browser. By the start of June, TempoFlex was working for my purposes and published to [GitHub](https://github.com/Fishbowler/tempoflex-chrome-extension).

At this point, it became a background project that I could use to learn. My strengths as an engineer lie mostly in testing rather than developing applications, and that testing occurs against applications built by others. I now had an application available with a single stakeholder, known needs, and I took the opportunity to expand my knowledge of implementing unit tests, and of what makes code easy & hard to test.

Other blog posts can talk as to why this is a terrible idea in practice, but as a learning exercise I sought for (and reached) 100% test coverage. Initially this was just plain unit testing. Some code was unreachable, so I tried test-time rewiring of private vs public methods, but that didn't work for the metric since the method under test wasn't the same as the one in the codebase any more. I then reworked a bunch of the tests as integration tests. After that, test fixtures were rewritten for readability and to reduce repetition. All the way through, there's a lot of refactoring as I'm head-scratching about how to make it testable. All highly rewarding.

Over the course of this, I enlisted the help of other folk at work to test changes and help me solve some of the more intractable problems that I was plainly too green to solve. It gained me some users, and in doing so, accidentally gained stakeholders with their own individual use-cases. What happens when someone logs tomorrow’s holiday today? What happens for users who joined the company during this calendar year? Is this how developers feel when testers test?

Over time, the issue tracker accrued issues, and those issues were resolved. Additional features were added too, such as SAST and dependency scanning and Firefox support.

Atlassian announced the demise of Jira Server in its current license model, which spelled an quick end to the usefulness of TempoFlex for that role. I look forward to picking up other projects in the future, and continuing to develop them in the open.

_This post was originally written in November 2020, and has been edited, because I hated my old writing._
