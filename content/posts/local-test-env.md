---
title: 'Local Test Environments'
date: 2023-10-13
categories : ["testing"]
draft: true
---

Dev, Int, Ref, Beta, Pilot, Pre-Prod, and lots of other labels for deployed environments of software that aren't The Production Environment.

What's the data?
Where can you get it from?
Can it be seeded?
Can it be updated automatically?
Can it be reset?
If you alter very core data, does it need restarting, because this is unusual? Is that easy to do?

Is it containerised?
What about running from IDEs?
Who's it for? A tester who wants everything, a Dev who wants everything but the component they're working on? Concurrent branches on multiple repos to deliver a feature.
Skills required. Running an API dev env might be pointless skills for a mobile dev.
Performance. Running a react app from IDE is heavy compared with pre-built things
What about a container that builds the code? Does that save some setup?
Container registries?

What is a full stack?
Authentication
API(s)
Async processors
Web
Reverse proxy?
Ngrok for ease of mobile?
3rd party component mocks?
What else? YMMV