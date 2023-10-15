---
title: 'Considerations for Local Test Environments'
date: 2023-10-13
categories : ["testing"]
draft: true
---

Dev, Int, Ref, Beta, Pilot, Pre-Prod, and lots of other labels for deployed environments of software that aren't The Production Environment.

But sometimes you just need your hands on it, to manipulate it the way you want, or to get the observability that you need. You need a local test environment.

Last time I planned a local test environment, I wrote some notes, and I've tidied them below.

## Data

* What is the data?
* Where can you get it from?
* Can it be seeded, to be placed in the database before the application launches?
* Can the seed data be updated automatically from another source, e.g. Production? Configuration is key.
* Can it be easily reset?
* If you alter very core data, like fundamental configuration, does a component (or more?) need restarting? Is that easy to do?

## Execution

* Is it containerised? Can it be? Should it be?
* What about running from IDEs?
* Who's it for? Is this just for you, or will others use it? A tester might want the entire stack, but maybe a Dev wants everything but the component they're working on (because they'll run it from their IDE)?
* Do you just want to run the latest code from the main branch? Or might you use this to test features before merging? If so, does that mean that everything is on main except the one component under test? Might you want to run concurrent branches on multiple repos that have all been altered to deliver a single feature (e.g. new endpoints on an API and a web app that uses them).
* What skills are required to run it? Can you make it easier? Building and running an API dev environment from an IDE might feel like unnecessary learning/effort to a mobile dev, for example.
* How fast do you need it to launch? How fast do you need it to run? For example, running a react app from an IDE is heavyweight, compared with running a pre-built web-app.
* Could/should you use a container to build the code as well as run it? Does that save some setup/friction for folk?
* Can you use Container Registries to store built versions, perhaps in your CI system?

## What's included?

* What counts as a full stack?
* Do you represent Authentication? Can you?
* Are you running APIs?
* Does you application include async/queue processors? Do you need to represent them locally? If you don't, what won't work?
* Is there a web app?
* Will you need to include a reverse proxy in order to avoid representing applications on different ports?
* Do you need Ngrok, e.g. to connect a mobile app up to your local env?
* Do you need any 3rd party component mocks, e.g. analytics?
* What else does your app have?

Your mileage is gonna vary as to how complete the above lists are for your environment, but hopefully it's useful.
