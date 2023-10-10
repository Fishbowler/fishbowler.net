---
title: "Coverage"
date: 2023-10-10
categories : ["testing"]
layout: post
draft: true
---

Recently, I was part of a discussion on LinkedIn about whether a Test Automation Engineer was required in order to reach 100% coverage of a set of a new features, or whether a group of developers could get there without the specialist expertise.

The answers already sufficiently covered the fact that outsourcing your test code to someone else is a bad idea.

My bigger concern was the idea that 100% coverage even exists at all.

### Given a simple form with a textbox and a submit button, there are infinite inputs

There's a near-infinite number of possible test combinations.

* There's just under 150,000 unicode characters for every position
* Length is also variable
* Even if the length were limited to, say, 500 characters that's already an astonishingly big number (a number over 2500 digits long!)
* Then add timings
* Then add delete actions
* What about copy'n'paste?
* We haven't even started on what the button does
* And how many times we can push it
* Can I right click anywhere?
* Then there's performance
* And usability
* And accessibility (although that might not take too long)
* And everything else

This could already take a lifetime.

If you remove the textbox, there are still nearly infinite tests we can think of.

Lots of them get grouped together into classes, where executing any one test might be equivalent to any other (e.g. 425 characters and 426 characters are likely the same) and lots of those entire classes can be deemed irrelevant or low-risk and discarded.

You don’t get to 100%, or ever _finish_ testing, you just choose to stop based on the risks you’ve thought of.
