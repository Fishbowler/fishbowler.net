---
title: "Michael Bolton's Test Rap: Scorecard Edition"
date: 2023-02-20
categories : ["testing"]
layout: post
draft: true
---

As part of his keynote at QAFest in Kyiv in 2018, Michael Bolton did a performance of his Test Rap, inspired by Hamilton.

He’s performed this a bunch of times over a number of years, with lyrics altering from time to time (since, like any test plan, or any software, it’s never “finished”), but one online source gave the lyrics as:

{{<blockquote>}}
Experimentation, learning, freestyle exploration

studying and modeling, conjecture, observation

test code development, task prioritization

checking out competitors, preparing simulations

reconciling your testing with required regulations

gathering, assessing, and applying information

deliberation, judgement, designing visualizations

setting up the lab to try complex configurations

working out the problems in a puzzling situation

finding ambiguity in a product specification

trying to look beyond the predicted expectation

that’s because testing’s all about investigation

questioning and learning-playful product interaction

trying to keep your focus while you’re managing distraction

sensemaking, myth-breaking, decision making, no faking

stressing out the product to discover where it’s breaking

refining test approaches through deliberate practice

how could hackers hack this? don’t give them access!

working with the marketers to show the app’s power

point to all the features try to finish in an hour

So I shall socialize to promote collaboration

other folks can help me with my testing preparation

talking with the managers to learn what they require

testing for charisma—that’s what customers desire

refactoring at every step keeping things maintainable

let’s get over overtime and make the pace sustainable

working with the marketers to show the app’s power

point to all the features try to finish in an hour

selecting, configuring, and then applying tools

applying critical thinking confirmation is for fools

pattern recognition, distributed cognition

helping shy colleagues get over inhibition

building coverage models, analyzing risk

eliminating waste, trying to keep the pace brisk

wrestling with problems in the setup of environments

interviewing users to discover their requirements

interrupted and disrupted ‘cos the product’s full of bugs

the fellas who developed it must have been on drugs!

I want to say this while I’m in a rap rhythm

a check’s a part of testing encoded in algorithm

testing’s much more than automated checks and test cases

human variation puts the product through its paces

use the tools powerfully, that’s what I’m suggesting

but don’t try to tell me you ca automate the testing!
{{</blockquote>}}

Now, given that Michael is a world-renowned expert on the topic of modern software testing, let us assume that this rap contains "good things", and make a further (possible spurious) assumption that it holds at least one mention of every important aspects of testing skill & activity.

Could we rate ourselves against the lyrics of a rap?

Here's an attempt...

| Lyric                                                       | Interpreted Meaning                                                                                                                                                                                                                                | Score |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| Experimentation, learning, freestyle exploration            | Do we confine ourselves to scripts, or do we allow ourselves to hypothesise and experiment and learn about the software under test?                                                                                                                |
| studying and modeling                                       | Do we take time to abstract the behaviour into a model, ask questions of the model, then translate them into tests of the real-world software? Instead of “this text field does this”, it’s “the system has these inputs and performs this action” |
| test code development,                                      | Automation, tools, scripting, CI, linting, and anything else code-based that gives a lens on quality or helps a human gain some insight.                                                                                                           |
| task prioritization                                         | Prioritising tasks based on their importance to the overall testing effort. Do we blindly take tickets in some natural order?                                                                                                                      |
| checking out competitors,                                   | Analysing competitor products to inform ourselves on Comparable Products as a risk heuristic (since if every other app works one way users could be confused if ours doesn’t)                                                                      |
| preparing simulations                                       | Simulating real-world scenarios to test the software under various conditions (e.g. network unreliability)                                                                                                                                         |
| reconciling your testing with required regulations          | Ensuring that the testing process and activity complies with relevant laws, regulations or standards for your business or sector.                                                                                                                  |
| gathering, assessing, and applying information              | Collecting information about the software and using it to guide the testing process. Testing is inherently a learning process, and this is probably the most important item on this list.                                                          |
| deliberation, judgement,                                    | Making informed decisions about how to test the software and how to action its findings.                                                                                                                                                           |
| designing visualizations                                    | Representing the findings of testing as images to support the teams understanding of the product                                                                                                                                                   |
| setting up the lab to try complex configurations            | Configuring more complex test environments and conditions to simulate realistic usage scenarios that might uncover risk.                                                                                                                           |
| working out the problems in a puzzling situation            | Troubleshooting issues, solving complex problems or understanding complex behaviours that arise during testing.                                                                                                                                    |
| finding ambiguity in a product specification                | Identifying areas of a product specification that are unclear or ambiguous, and working to resolve those issues.                                                                                                                                   |
| trying to look beyond the predicted expectation             | Thinking creatively and trying to anticipate how users may use the software in unexpected ways.                                                                                                                                                    |
| questioning and learning-playful product interaction        | Interacting with the software in playful ways to uncover issues and learn about its capabilities.                                                                                                                                                  |
| trying to keep your focus while you’re managing distraction | Staying focused on the testing process even when distractions or interruptions occur.                                                                                                                                                              |
| sensemaking, myth-breaking, decision making, no faking      | Using critical thinking skills to make informed decisions and challenge assumptions about the software.                                                                                                                                            |
| stressing out the product to discover where it’s breaking   | Testing the software under extreme conditions to uncover any weaknesses or issues.                                                                                                                                                                 |
| refining test approaches through deliberate practice        | Continuously improving the testing process through deliberate practice and refinement of testing techniques.                                                                                                                                       |
| how could hackers hack this? don’t give them access!        | Considering potential security vulnerabilities and testing the software with the mindset of a malicious hacker.                                                                                                                                    |
| working with the marketers to show the app’s power          | Collaborating with marketing teams to showcase the software's capabilities to potential users.                                                                                                                                                     |
| point to all the features try to finish in an hour          | Quickly demonstrating all the software's features to potential users in a limited amount of time.                                                                                                                                                  |
| So I shall socialize to promote collaboration               | Networking and building relationships with colleagues to promote collaboration and knowledge sharing.                                                                                                                                              |
| other folks can help me with my testing preparation         | Seeking input and assistance from other team members to prepare for testing.                                                                                                                                                                       |
| talking with the managers to learn what they require        | Communicating with managers to understand their expectations and requirements for the testing process.                                                                                                                                             |
| testing for charisma—that’s what customers desire           | Testing not only for functionality but also for the software's overall appeal to customers.                                                                                                                                                        |
| refactoring at every step keeping things maintainable       | Modifying the code to improve its quality and maintainability while testing                                                                                                                                                                        |
| let’s get over overtime and make the pace sustainable       | Avoiding working overtime to ensure that testing is done at a sustainable pace                                                                                                                                                                     |
| working with the marketers to show the app’s power          | Collaborating with marketers to highlight the app's strengths and features                                                                                                                                                                         |
| point to all the features try to finish in an hour          | Demonstrating all the app's features within a short period                                                                                                                                                                                         |
| selecting, configuring, and then applying tools             | Choosing the right tools for testing and configuring them for the project                                                                                                                                                                          |
| applying critical thinking confirmation is for fools        | Emphasizing the importance of critical thinking and questioning during testing rather than relying solely on confirmation bias                                                                                                                     |
| pattern recognition, distributed cognition                  | Using pattern recognition and distributed cognition to understand complex systems and identify potential issues                                                                                                                                    |
| helping shy colleagues get over inhibition                  | Supporting and mentoring colleagues who are hesitant or lacking confidence in testing                                                                                                                                                              |
| building coverage models, analyzing risk                    | Developing coverage models and analyzing risk to ensure thorough testing                                                                                                                                                                           |
| eliminating waste, trying to keep the pace brisk            | Minimizing unnecessary activities and trying to maintain a fast pace during testing                                                                                                                                                                |
| wrestling with problems in the setup of environments        | Troubleshooting issues with the setup and configuration of testing environments                                                                                                                                                                    |
| interviewing users to discover their requirements           | Conducting interviews with users to identify their needs and requirements for the software                                                                                                                                                         |
| interrupted and disrupted ‘cos the product’s full of bugs   | Facing disruptions and interruptions during testing due to the presence of bugs in the software                                                                                                                                                    |
| a check’s a part of testing encoded in algorithm            | Acknowledging that automated checks are an essential part of testing, but they are not the only form of testing                                                                                                                                    |
| testing’s much more than automated checks and test cases    | Highlighting that testing is more than just automated checks and test cases and involves human variation and critical thinking                                                                                                                     |
| human variation puts the product through its paces          | Emphasizing that the uniqueness and variation in human behavior put the product to the test during testing                                                                                                                                         |
| use the tools powerfully, that’s what I’m suggesting        | Encouraging the use of testing tools to their full potential                                                                                                                                                                                       |
| but don’t try to tell me you can automate the testing!      | Acknowledging the importance of automation in testing but also recognizing that testing involves human variation and critical thinking that cannot be entirely automated                                                                           |
