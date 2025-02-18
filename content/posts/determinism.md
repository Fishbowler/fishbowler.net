---
title: "Determinism in Tests"
date: 2025-02-17
categories : ["testing"]
layout: post
draft: false
---

Software is deterministic. It's a computer program, after all. It's a series of instructions that, when executed, will always produce the same output given the same input. Our inputs might be literal inputs, or might be actions. There are also implied inputs that make up the test environment. One example might be available disk space.

Testing is a learning activity, where for a given set of inputs we learn about the output. We can then evaluate that output in terms of correctness, performance, usability, or any other quality attribute, and highlight differences with expectations, and the risk to value. One test could be defined as a set of inputs that we're interested in (and that applies to functionality, accessibility, performance).

The real problem is... we never _really_ know our inputs. We only know some of them. Whilst we have control of the explicit inputs and actions, we never really have control of our test environment. An application runs on an operating system, which has complex behaviours that we can't predict and we can't control. Task scheduling, hardware and network interrupts, and other processes all have the possibility to make a difference on the application under test.

So if we don't know the inputs, what does a test tell us? I think it probably says that for a given set of inputs, it's _likely_ that this is the output. In most situations, that's good enough to have confidence in a risk decision. Where it isn't, we can repeat the tests a number of times and see if the output is consistent. Over time, we might identify inputs that affect the outputs, and find new ways to exert control over the test environment.

This post was inspired by a conversation this morning between engineers on the value of a memtest86 result, and [this talk](https://fosdem.org/2025/schedule/event/fosdem-2025-5081-enhancing-testing-strategies-for-critical-systems-statistical-path-coverage/) by Imanol Allende from FOSDEM 2025.
