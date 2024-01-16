---
title: '30 Days of Automation in Testing - Days 1 to 4'
date: 2018-07-11
categories : ["testing"]
draft: false
layout: post
---

[![](https://d2h1nbmw1jjnl.cloudfront.net/lesson_resources/resources/000/000/179/original/Automation_in_Testing_Badge.png?1530193025)](https://d2h1nbmw1jjnl.cloudfront.net/lesson_resources/resources/000/000/179/original/Automation_in_Testing_Badge.png?1530193025)

  
  
  
I've been meaning to complete one of the Ministry of Testing's [30 Days of Testing](https://www.ministryoftesting.com/dojo/series/30-days-of-testing) challenges for a while. I got about two thirds of the way through the first one as a team exercise, then everyone "got busy with other things", and it died a horrible death, with the checklist languishing on the wall for a couple of months as a reminder of how we'd failed.  
  
When the latest one, [30 Days of Automation in Testing](https://www.ministryoftesting.com/dojo/lessons/30-days-of-automation-in-testing), was announced I tweeted this:  

{{< tweet 1012595452708118528 >}}

And so here we are, with 11 days of July done, and I thought I had better start writing up what I've been doing & thinking so far.  
  
**Day One** \- _Compare definitions of "automation" and "test automation"._  
I don't think I quite appreciated how stark this was going to be. Don't get me wrong - this was like a leading question - we all knew these definition were gonna be incongruous.  
  
Automation - methods and systems for controlling other external systems, appliances and machines.  
Test Automation - a big mixed bag. Skills, frameworks, packages, test drivers, even the tests themselves.  
  
Were I to take what I know about the field of test automation, and attempt to use the definition of automation to identify what within that field is "the automation", it's a big circle around everything that resides on the machine up to, but not including, the software being "automated". To be clear, in a Selenium-type context, "the automation" includes:  
  

*   nothing of the human
*   the high-level language in which the tests are written (e.g. JavaScript, Java)
*   any cucumber-type fixtures and any other sprinkles you like in your repo
*   the libraries which enable and structure those tests (e.g. mocha)
*   the engine that provides the external interface (e.g. Selenium)
*   possibly any purpose built third-party access mechanism, like the WebDriver implementation for/within your browser

From here, we've got "a system for controlling the external system" - the website running in the browser.

  

  

  

**Day Two** \- _Share something from an automation-related book by Day 30_

It's not Day 30 yet. I've had a few books on my todo list for a little while, but Alan Page's [AMA on Modern Testing](https://www.ministryoftesting.com/events/testing-ask-me-anything-modern-testing-alan-page) has bumped his book on Leanpub, [The "A" Word](https://leanpub.com/TheAWord), right up my list. Gonna try to tackle that this month.

  

  

**Day Three** \- _Contribute to the Club about automation_

  

I spoke [here](https://club.ministryoftesting.com/t/what-api-automation-testing-tool-you-use-and-why/16424/11?u=dancaseley) about my experience choosing an API test tool. It's a topic I've been revisiting internally, where I've now got a new role in a new company, wondering if I should stick to what I know, or whether a new context requires a new tool.

  

  

  

**Day Four** \- _Describe what types of testing automation can help with_

  

Sounds like a straight up exam question, no?

  

The bog standard answer: regression testing. I can check a subset of pre-existing functionality that previously worked still operated to predetermined standards using some prior-written code.

  

But that's the boring answer.

  

The real meat here is in feeling the boundaries.

*   I don't find automation over accessibility gives me any confidence at all, but some tools can identify some things that almost probably wrong.
*   Automation on usability is impossible (for some definitions of usability)

*   If you include rendering here, then visual checking for browser compatibility comes in, and I do find that cheap & sexy. Viv Richards speaks well about this [online](https://twitter.com/11vlr/status/1014960594896769024), and spoke about it to a packed room at NottsTest earlier this year.

*   I love using automation to explore an API. I can sit with 5 lines of code, written as a positive check of a particular endpoint and play with it to explore the behaviour. What if this value were larger, or longer, or omitted?
*   I mentioned in my post on the MoT Club about using automation for monitoring - if it's good enough to give you confidence to release, why not use a subset of those checks to establish if it's still running later?

Automation isn't just about testing, though. I regularly script my way around problems. I had a test environment that got trashed regularly, and each build required fetching a dozen packages from a few different online repos. Since the versions were locked, I scripted the fetch. Then took it a step further and popped the output into S3, and scripted the pull, unzip and install of the contents. Effort: 1hr. ROI: Eleventy five inside a week. That's not test automation, but it certainly feels like automation in testing.