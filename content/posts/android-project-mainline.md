---
title: "What is Android’s Project Mainline, and what will it do for business?"
date: 2019-09-06
categories : ["technology"]
layout: post
draft: false
---

Here we are in early September, and Android 10 has just been released. It’s got lots of new features that might excite average users:

* Dark Mode
* Theming
* Gesture navigation
* Inbuilt screen recording
* WiFi Easy Connect

It also contains features for the more technical and security-conscious users

* Support for 5G networks
* Peer-to-peer WiFi connections
* TLS 1.3
* Granting location permissions to apps only whilst in the foreground
* MAC address randomisation

There’s plenty more out there, and plenty of news outlets are publishing big lists you can find if you want to know more. Whilst some of these above might be also be of interest to businesses and business users, it’s the new Project Mainline that should be the feature of particular interest to a business. Whether you’re managing your own device fleet, or you’re into BYOD, Android can be a security headache. On the one hand, they’re much more open – much of the core source code is open for review, and they publish detailed security changelogs. On the other hand though is Android’s own personal f-word. Fragmentation. Fragmentation is a headache for patching and updates. This has meant the premature death of many an Android device, not because it doesn’t have the latest features desired by users, but from businesses retiring a device model from their estate because of some vulnerability that Google has fixed but the OEM won’t ship.

Project Mainline is a major step forwards in solving this security problem.

This feature, coming in Android 10, allows components of the core operating system to be updated via the Play Store, often without a reboot. Like the Play Store app itself, or the Google Play Services app in the background, this won’t be an optional update that occurs under user control (or can be snoozed forever!) but instead a background job that takes care of everything.

Components that can be updated by Project Mainline (source: [Android Developers Blog](https://android-developers.googleblog.com/2019/05/fresher-os-with-projects-treble-and-mainline.html)):

* Security: Media Codecs, Media Framework Components, DNS Resolver, Conscrypt
* Privacy: Documents UI, Permission Controller, ExtServices
* Consistency: Timezone data, ANGLE (developers opt-in), Module Metadata, Networking components, Captive Portal Login, Network Permission Configuration
A recent example of where this would help: [CVE-2019-9506](https://nvd.nist.gov/vuln/detail/CVE-2019-9506), aka [KNOB Attack](https://knobattack.com/).

In this vulnerability, a third party attacker can modify the negotiation between two bluetooth devices to lower the entropy of the encryption key to 1 byte, allowing for a relatively easy brute-forcing of the key. This attack works on devices that have already been paired, and would allow the attacker to read, add or modify the communication between the two parties.

Google haven’t given stronger details beyond the above on what will be patchable via Project Mainline, but “Networking components” is on the list. This is already a patched vulnerability, available in August’s 2019-08-05 security patch ([here](https://source.android.com/security/bulletin/2019-08-01#2019-08-05-details)). This is great for a Pixel device, or for devices with strong updates via OEMs (OnePlus and Nokia doing great here!), but for most other devices, these patches will be delayed or non-existent. A device supported by Project Mainline (i.e. any Android 10+ device) would always get patches, and even presently OEM-supported devices wouldn’t need to wait for the monthly patch cycle – a new patch could be circulated as soon as it is ready. Google have even invited OEMs to collaborate with them on testing, such that your device should never be degraded by a patch, only ever improved.

The single caveat is that we can’t expect this to change overnight. The most recent [distribution numbers](https://developer.android.com/about/dashboards) from Google show that Android 9 was on just over 10% of running devices a full nine months after its release. Speed of availability aside, Android has higher-than-average uptake amongst technically-savvy users, but lower-than-average uptake by security-conscious businesses. This is a smart and very welcome move on Google’s part.

I’m pleased to have a device running Android 10, and looking forward to seeing my device of choice more readily adopted by businesses, being a first class citizen in BYOD, and less often getting the shifty eye from the security guy for bringing a potentially insecure device into our company network.
