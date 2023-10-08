---
title: "Is it a bug?"
date: 2023-01-13
categories : ["testing"]
layout: post
draft: true
---

## What counts as a bug?

{{< blockquote >}}
Heads-up: This post won’t get into IEEE discussions of Fault vs Failure, neither will it look at ISTQB, ISO, or any other body’s definition of words that may or may not apply within a given context.
{{< /blockquote >}}

If a bug is a breakage of some kind that we want to fix, where is the line? What makes it a bug? Or, what makes something not a bug?

### Does it need to be broken?

Does something need to be non-functional to be a bug?

Of course not. We’ve definitely seen past instances where Ugly is a bug and where Slow is a bug.

### Is it the user?

Does a bug require an effect on a user?

Maybe not. We’d consider a performance problem that spiked hosting costs by 10x with no discernible user effect to be a bug.

### Does it require human error?

Does a bug need to be caused by mistake in code or configuration to be a bug?

Probably not. If the unchanged software was faulty on the next version of Chrome, we’d probably manifest that as an interoperability bug.

### Does it need to happen all of the time?

If I see a problem once in the app, but can’t do it again, is it a bug?

This gets more philosophical. If I got the software to behave erroneously once, then some set of conditions exist for that to occur. If I can’t reproduce the issue, I’ve not recreated the correct conditions. Yet. A bug exists, but I might not be able to explain it well enough for it to be actionable.

It's normally another daylight savings time bug...

### Conclusion

Perhaps it’s enough to say that we want to put right something that is:

* noticed by someone 1+ times
* affects someone
* considered to be “wrong” in any degree
* something we sufficiently care about
