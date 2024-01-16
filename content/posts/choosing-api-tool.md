---
title: 'Choosing an API tool'
date: 2018-05-02
categories : ["testing"]
layout: post
draft: false
---

[![](https://1.bp.blogspot.com/-hDOhHLvBGlM/WuhJj_l_X1I/AAAAAAAA4c4/o2encvwYQSwhmdk2NHHsqPvzW_nbR5d6ACLcBGAs/s320/keys-workshop-mechanic-tools-162553.jpeg)](https://1.bp.blogspot.com/-hDOhHLvBGlM/WuhJj_l_X1I/AAAAAAAA4c4/o2encvwYQSwhmdk2NHHsqPvzW_nbR5d6ACLcBGAs/s1600/keys-workshop-mechanic-tools-162553.jpeg)

  
  
A story about selecting tools from my previous job.  
  
In the dark days, we explored as a user would, and when things changed, we explored again.  
  
Later, it got lighter, and we used tools like Fiddler to help us explore. We saw more, and we used our tools to explore deeper than we could before.  
  
Before too long, we started automating.  
  
One time, we encountered a problem where we needed to know if a piece of common markup (in this case, a support popup) displayed correctly in all of our sites, in all of the browsers and in all of the languages. We automated visiting all of the pages on which this markup was displayed, taking a screenshot, then quickly reviewing the hundreds of outputs. The cost/benefit was obvious here - one person achieved more with browser automation in a day and a half than a group of people could have done using manual methods.  
  
Later, we used our browser automation skills on other tasks and on other projects - some of it was for confidence in the project, and some was for confidence in the live environment (i.e. used for monitoring).  
  
Important people saw this work and they wanted to see more of this. So we stopped.  
  
  
  
  
Automating all of the things isn't necessarily beneficial, especially not when you're using a heavyweight tool (in our case Nightwatch.js and Selenium). We didn't want to build a massive body of tests where all of the variants were taking many seconds to iterate through. We needed to cover these with something more lightweight, and only use the UI tests when we need them.  
  
  

[![](https://image.slidesharecdn.com/promisecloudnative-enterprise-160505211615/95/the-promise-of-a-cloud-native-platform-20160504-7-638.jpg?cb=1462483127)](https://image.slidesharecdn.com/promisecloudnative-enterprise-160505211615/95/the-promise-of-a-cloud-native-platform-20160504-7-638.jpg?cb=1462483127)

(Image source: [Slideshare.net](https://www.slideshare.net/bridgetkromhout/the-promise-of-a-cloud-native-platform-20160504))

  
We do want to automate more of the things. We just don't want it to take hours running them through a real browser. We also don't want to automate everything just because we can - we want the things that are important to us, and will give us real information and confidence in an acceptable timescale.  
  
Our next step: API Tests.  
  
When we began automating using Nightwatch, we were a test team of 2. Now we're a test community of 6, working in a squad structure. Co-ordinating time isn't as easy. We couldn't simply ease this in. We'd need some sort of "big bang" effort, else people would be left behind because of the "impending deadline" for the "current important thing". I got buy-in from the squad leads, booked a meeting room for an afternoon, and told everyone to come prepped for API Testing Fun with a tool of their choice. Everyone was excited to get into this. A few of us had done some little bits of API testing before through a mix of Postman, Fiddler, JMeter, Runscope, PowerShell and JavaScript, but here, we all committed to use a new tool that we hadn't used before. I'd done the most API testing previously, so took to public APIs to come up with challenges for the session that people would solve with their tools, the idea being that the challenges would represent those seen within our domain (e.g. GET/POST, redirection, OAuth), and other than me, nobody had any domain knowledge advantage. We'd use a 30 minute block the next day to debrief.  
  
_For discovering APIs for the challenges, I stuck to things I'd used in the past plus a small amount of googling. If you don't have this, or want some variety, try [https://any-api.com/](https://any-api.com/) for some public and well-documented APIs. I wish I'd known about this then..._  
  
The session was fantastic fun. We had a mix of skills where some people were naturally bent towards an aptitude for this sort of thing, and it naturally lent itself to pairing when people solved quite how apps authenticated with Twitter (this wasn't trivial, and the docs felt fragmented).  
  
At the end of this session, we'd eliminated a few tools as being not feature rich enough for our use cases, or plain too ugly or hard to use. We ditched pyTest, Karate and a couple of others. We ditched everything except [Postman](https://www.getpostman.com/) and [Frisby.js](http://frisbyjs.com/), as these seemed most capable of completing the tasks.  
  
I was investigating Frisby for this session, and you can see the challenges I set and my work to solve them on [GitHub](https://github.com/Fishbowler/frisby-evaluation).  
  
We regrouped two weeks later where we ran a second session. We each picked either Postman or Frisby (except the two of who used those tools previously - we switched). I provided a new set of challenges, this time inside our business domain - real tests against our live APIs. Given the limited amount of experience most people had gained on API testing by this point, this was still a non-trivial effort. We learned loads and gained velocity given that we had the domain knowledge. The result of the session? Surprisingly inconclusive.  
  
As it turns out, these tools have different strengths and are useful for different things. We decided that Postman was great for exploratory testing and Frisby was great for regression testing. Postman has a testing ability, but felt primitive compared to what you can do in Frisby. Frisby _could_ be used for exploratory testing, but it'd be time consuming. We decided to start implementing regression tests in code whilst also purchasing Postman Pro licenses for the team to use for feature work.  
  
The team felt enabled - every time we considered automating a browser interaction, we could immediately consider pushing UI tests to API tests.  
  
Of course, the journey doesn't end there. When can you push an API call to a simulated calls in an integration test? And so on to component tests, then to unit tests.