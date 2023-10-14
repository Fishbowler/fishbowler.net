---
title: "Testing and the threat of ChatGPT"
date: 2023-10-14
categories : ["testing"]
layout: post
draft: true
---

In late 2022, ChatGPT became available to public, sparking a new commercial battleground for conversational and generative AI. Since then, Google's Bard and Microsoft's Bing and Copilot systems have launched, and many have tried these systems and lauded the abilities of the machine to create many paragraphs of text and swathes of code in a fraction of the time that it would've taken even the most motivated of humans.

Testers in particular observe these tools and their ability to generate high-level strategy, concrete test plans, a litany of test ideas, replete with relevant test data, and code to implement basic checks for all of these. A week's work just got reduced to five minutes of “now write me one of these”.

This leads many testers to worry. If the machine can do this, is my job safe?

It’s a reasonable question. Technological advancement naturally gives the jobs of humans to computers that are cheaper and more consistent. If a generative AI can create the output of the tester, why would you hire a tester?

Testers are knowledge workers. They’re hired for their hard won experience with software. It’s this experience that allows them to create a good strategy, a good plan, a good list of test ideas, good test data and good checks. The generative AI is trained by a whole bunch of the internet up to 2021. Presumably, it will have seen test documentation and code elsewhere and is able to generate something similar. Maybe it’s got everything it needs?

Except… two little things.

Firstly, it doesn’t learn. Sure, it’s read the internet, and it can also learn from usage. Testers could teach it what a more appropriate set of test data might be, I suppose (except that we maybe just sacked them all). What it cannot do is make a plan, see something in the software, or get some additional context from a meeting, and adjust that plan on the fly. Even if they could get this from additional prompts, it won’t become more adept at using a singular piece of software, it won’t know to double-check the user profile page because that’s been broken a few times recently, or to pay special attention to the look and feel of the top carousel as it’s a revenue generating piece of content. It won’t ever get better at writing test plans for this software specifically. If it could be as good as a tester, it’d only ever be as good as that tester was on their very first day.

Secondly, the bot was only able to generate those things in response to a considered prompt by a tester. A more vague prompt would give a less precise generation, and one that used incorrect terminology could generate something useless. Something that obviously wrong is easy to spot. Something that’s subtly wrong isn’t nearly so easy, and would require someone with testing skill to spot and to correct, either by hand or using a follow-up prompt. The important thing here is that the input, the all-important **context** comes from the human.

If the AI is performing a task that you understand and saves you time, that’s excellent. If it’s doing something you don’t understand, where you can’t validate or correct the output, you’re using the tool incorrectly, and taking risks.
