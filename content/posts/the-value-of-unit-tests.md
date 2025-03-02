---
title: "The Value of Unit Tests"
date: 2025-03-02
categories : ["testing"]
layout: post
draft: false
---

I was asked by a friend recently about the purpose of unit tests in a project. I've written a little about this in the past, both very recently when talking about [Swiss Cheese / Layered Testing Cake]({{< ref "swiss-cheese.md" >}}) and I specifically didn't speak it about it all when talking about [The Value of Automation]({{< ref "the-value-of-automation.md" >}}), but this question came from a developer and I wanted to try to answer the question directly.

### The purpose of the tests

Unit tests tend to have value in two places in a developer's journey from the previous state of the project to the next state of the project.

- The New Stuff works
- The Old Stuff still works

The first is the most obvious. When you write a new piece of code, you want to know that it works. You want to know that it works in the way you expect it to work, and you want to know that its interfaces with its neighbours operates as you'd expect. This is the most common use of unit tests, and the one that most people think of when they think of unit tests. It's the one they teach us at nerd school.

The second is something that you should naturally get through the accrual of new features. As each feature is added, the number of unit tests grows, and the old features are tested along with the new features every time the tests are run, and give some sense of confidence that the integration of the new feature didn't break stuff. In reality there's another way these often get added. Bug reports. When we find a bug in a running system, as well as knowing that the system isn't operating as it should, it's also an indicator that the testing has failed along the way. As part of fixing the bug we add a unit test to prove the fix, and fill any other gaps we spot at the same time (e.g. maybe we've missed a class of test like null values, or a combination of inputs that we hadn't considered).

### Test styles

Unit tests are typically considered as passing a combinations of inputs to functions and asserting on the outputs. The outputs are both explicit return values, but also other effects, like a file existing or a database row existing, where the filesystem or database are replaced with mocks, fakes or stubs in order to detect the effect. This doesn't just apply for application-external entities - it can also apply for other entities inside the application, external to the unit under test, i.e. when an effect of the method is to call another method in another object. Where we've got these non-explicit effects, there are two ways to go about asserting the behaviour. These are called London and Chicago style assertions. Chicago style asserts on the effects of the method, whereas London style asserts on the interactions of the method. Chicago style is looking at real results - what was the end result of the method under test? London style does it differently, looking at what was called - did the external thing get called, and with the right parameters? Both have their place, both have benefits and blind spots, and different refactoring complications. A process that deals in results works at arms length - it allows the internals to change without breaking the test. A process that deals in interactions can be more resilient to changes in the external world, but ties your tests to the dependency map of the internal system.

### Additional testing

Just because you use a unit testing framework, doesn't mean that you need to stick to pumping variations of data through a function's method signature. Unit test frameworks are often used for wrapping other kinds of tests. Snapshot tests are a prime example used in the front-end development to validate that the current version of the code produces the same DOM as the previous version (and where if no version exists, it creates one that will stand as the 'golden' snapshot for the next one). Similarly, it's common to use unit tests for parsing and for serialisation/marshalling tests to ensure data structures are preserved across operational boundaries, or validating data structures in memory or on disk against a schema. 

### Patterns of tests

At the end of the day, what matters is that your tests have value, and that their implementation and maintenance cost doesn't exceed your threshold. That being said, there are patterns that can help both readability and maintenance.

In terms of maintenance, firstly, test one thing. One unit, if you will. Attempting to test "caching" or "databases" rather than one method or operation will create complexity that can't be understood or maintained by others, and adds ambiguity to what the problem is if the test fails. Next, finding the right balance of granularity of control is important (ignoring the illusion of [determinism]({{< ref determinism.md >}}) of course). If your tests are too tightly coupled to their implementation, not only do you have double the work to do every time you refactor, but you also have a test that's less tied to the intent of method, and less likely to catch a bug. You also introduce the risk that you're not counting your convoluted test infrastructure, and you end up testing that your mocks or fakes behave exactly as they should :D

In terms of structure, readability is key. Too much abstraction and you'll never be able to follow why a test failed, and possibly introduce so much into your test infrastructure that it itself should be tested. Too little work on abstraction and readability and you'll create tests so long that their intent isn't clear, and they scare off new contributors in your team. A useful pattern common across languages for this is the AAA pattern - Arrange, Act, Assert. In the Arrange stage of the test, data is created and dependencies are set up in the way needed for the test. In the Act stage, the code under test is called or triggered. In the Assert stage, the results are checked. This pattern is useful because it's easy to follow, and it's easy to see what's going on in the test - a failure is likely to always be in the last few lines of any given test. It's also easy to see where the test is doing too much, because one stage will be too long. More that anything, if your test doesn't fit into this pattern, there's a chance it needs to be rethought. For example, Arrange, Act, Assert, Act, Assert, Act, Assert is probably a smell that you're testing too much in one test.

There's enough to say about unit tests that a book could exist on the subject. In fact, several do. Hopefully this gives a good overview of the value of unit tests in a project. If not, expect updates...
