---
title: "Three Things I Learned This Week - 22nd Feb 2020"
date: 2020-02-22
tags : ["3things"]
categories : ["learning", "technology"]
layout: post
draft: false
---

To see why I write these, see my [first post]({{< ref "3-things-i-learned-20200215.md" >}}) in this series.

This week:

* iOS Network Extensions look like an awesome way to achieve some things that are easier on Android, but still not often used (like starting a VPN, or creating a proxy server). Whether it's hard or easy, rarer used technologies are harder to search for on Stack Overflow.
* Amazon have launched ["multi-attach" for EBS volumes](https://aws.amazon.com/blogs/aws/new-multi-attach-for-provisioned-iops-io1-amazon-ebs-volumes/). That means you can attach a disk to _sixteen_ computers at the same time. The engineering involved in this is astonishing. I've had problems with a disk attached to one machine and applications fighting over write access. Sure, it comes with the caveats that you want cluster-aware filesystems, etc., but Amazon are in the business of keeping your stuff running, and they're saying it's good to go. It'll be interesting to see how usage will compare to S3 for read-only filesystems when you need more than just 1 or 2 files on a whole bunch of application nodes.
* High-end sewing machines encompass touch-screen devices and cloud services. For example, the [Husqvarna Viking Designer Epic 2](https://www.sewessential.co.uk/husqvarna-viking-designer-epic-2) includes mySewnet as an integral feature for patterns - you can see from a glance at the image that it's a sewing machine with a very sizeable touchscreen embedded, obviously intended as a core part of the workflow. You don't need to click that link - beyond the embedded touchscreen, the important fact is that this appliance is an eye-watering _nine thousand pounds_. One assumes that for that money, you'd expect the device to last a while, yet like so many appliances now, lots of the value is in the interop with an online service that is in no way guaranteed to continue. Is this a planned obsolescence, to combat the problem of high-end machines lasting a lifetime, maybe?

Some bonus observations:

* Every time I look at XMPP, I learn a little more about how people are using it, and the amount of work that regularly goes into evolving it. If you've got a use case, there's a good chance that someone else has had it already. They might've [extended XMPP](https://xmpp.org/extensions/) to support it, or maybe your favourite XMPP server has a [plugin](https://www.igniterealtime.org/projects/openfire/plugins.jsp) for it.
* People say naming stuff is hard. It isn't. Explaining stuff is hard. Teaching stuff is hard. I've never seen it explained better than this quote from a Google employee:

{{< tweet 1227344603847823360 >}}
