---
title: "Stop Rotating Your Passwords"
date: 2018-03-14T15:40:24+06:00
image : "images/okta_settings.png"
# author
author : ["Nick Selby"]
# categories
categories: ["authentication","access control","SSO","Best Practices"]
tags: ["phishing","ransomware"]
# meta description
description: "Phishing is the most common vector for ransomware. Phishing your staff is not the solution to phishing."
# save as draft
draft: false
---

**I’ve been [arguing](http://searchwindowsserver.techtarget.com/news/1281083/Bypassing-password-downfalls-with-single-sign-on) for [years](https://www.infoworld.com/article/2618482/new-year--same-old-security-passwords.html) that we in information security aren’t doing anyone any favors when we demand that people use for passwords something impossible to remember, then we demand that they remember it, and then we insist that, for God’s sake, they never write it down.**

And as if we weren’t bad enough, soon regulators came along and made it worse: “Rotate your passwords every 90 days,” they sagely intoned, “to make them more secure.”

They’re wrong. 

Forced password rotation, or password expiry, is just a big stupid thing to do. The problem now is convincing auditors that you’re OK to stop doing it — overcoming dogmatic adherence to a dumb thing is not easy.

But it’s possible.

Here’s how to justify Password-Expiry-Only-on-Suspicion-of-Compromise to your auditors:

## Let Me Sum Up: ##

[NIST Special Publication 800–63B guidance](https://pages.nist.gov/800-63-3/sp800-63b.html#sec5)

[National Cyber Security Center guidance](https://www.ncsc.gov.uk/guidance/password-guidance-simplifying-your-approach)

[Chastney On Password Expiry](https://blogs.dxc.technology/2016/04/18/is-it-time-to-stop-expiring-passwords/)

[Cranor on Password Expiry](https://www.ftc.gov/news-events/blogs/techftc/2016/03/time-rethink-mandatory-password-changes)

## How I Got Here ##

The topic came up for me again recently when revamping the information security program at a financial institution. This is a place that has gone to some pretty reasonable lengths to protect themselves: They know who their users are, and what they are permitted to do, on what devices, with what configurations, from which locations. They’ve got well-managed machines, and Single-Sign On, and they require push or XOTP-based second-factor authentication for everything they use. And sometimes, they require something you know, and two things you have.

And now, here was a regulator asking them to audit regularly not just what was accessed, and when, and by whom, and whether each user was Kosher, but also, the last time the person’s password was changed.

You know, for security.

The chief engineer was incredulous. “Rotate passwords? We get a new password every time.”

And even if we didn’t — even if we just had single-factor — rotating passwords is just ... Stupid.

As I often do when I’m apoplectic, I tweeted.

![nselby tweet 2018](/images/nselby_tweet.png "Tweet from nselby 12 March 2018")

And, lo! wisdom arrives minutes later from [@wendynather](https://twitter.com/wendynather):

![Wendy Tweet](/images/wnather_tweet.png "Wendy Response Tweet")

## Homeopathy for your Network ##

The argument about whether changing passwords is more secure is also far less established scientific fact than simple common belief. Researchers at the School of Computer Science, Carlton University, Ottawa, [state that](http://people.scs.carleton.ca/~paulv/papers/expiration-authorcopy.pdf) 

> “The historical idea is that [regular password changes] increases security — although the implied gain has never been quantified.”



## Rotating passwords: an expensive placebo security measure. ##

Indeed, the disruption, and the number of man-hours wasted and user frustration as they need to do password resets associated with their needless password updates make this exercise a significant disruption to our business with no evidence of increased security.

It is simply expensive effort to achieve a placebo security measure. It’s homeopathic enterprise security. It’s the TSA for your network.

I’ll go you one farther: I argue that not changing the static password is more secure than changing it every 90 days.

That’s because if — like ours — the static password is strong and secure (in our case, it uses at least ten characters that must include mixed upper and lower case, and at least one number and one special character), then forcing users to remember another such inherently un-memorable password actually encourages bad practices such as re-using old passwords, making [predictable variations from existing passwords](https://www.youtube.com/watch?v=7htBb-w9fNw), or writing them down.

This is not a crazy idea, or one that is out of left field. It’s certainly not original. And it’s taking hold in some pretty conservative places.

In 2016, Lorrie Cranor, Chief Technologist of the Federal Trade Commission wrote in an [official FTC publication](https://www.ftc.gov/news-events/blogs/techftc/2016/03/time-rethink-mandatory-password-changes), 

> “there is a lot of evidence to suggest that users who are required to change their passwords frequently select weaker passwords to begin with, and then change them in predictable ways that attackers can guess easily. Unless there is reason to believe a password has been compromised or shared, requiring regular password changes may actually do more harm than good in some cases.”

Then [Chris Swan](https://medium.com/@cpswan) tweeted something that would make my life significantly better:

![Chris Swan Tweet](/images/cpswan_tweet.png "Chris Swan response tweet")

Chris (if you don’t know him you [should](https://twitter.com/cpswan), because it is nice to have at least one friend who lives [five years in the future](http://blog.thestateofme.com/)) is talking about [NIST Special Publication 800–63B guidance in Section 5.1.1.2](https://pages.nist.gov/800-63-3/sp800-63b.html#sec5), “Memorized Secret Verifiers” — that’s “password” to you:

> “Verifiers SHOULD NOT require memorized secrets to be changed arbitrarily (e.g., periodically). However, verifiers SHALL force a change if there is evidence of compromise of the authenticator.” [Emphasis in original]

A year earlier, the UK Government’s National Cyber Security Centre [reached the same conclusion](https://www.ncsc.gov.uk/guidance/password-guidance-simplifying-your-approach), saying,

> “Only ask users to change their passwords on indication of suspicion of compromise.”

Chris pointed me to a great article by Graham Chastney, a technologist at Chris’ firm, DXC, that [Chastney wrote when the UK NCSC (then CESG) guidance mentioned above came out](https://blogs.dxc.technology/2016/04/18/is-it-time-to-stop-expiring-passwords/).

That article is worth a read, but don’t miss a nice related piece on Chastney’s personal blog, [The Four Ages Of Remembering a New Password](https://grahamchastney.com/2011/09/09/the-four-ages-of-remembering-a-new-password/).

## Regulators ##

Oh, by the way: when dealing with regulators we speak with, it’s nice to deal with woke ones. When I ran all this by them, I was delighted to see that they agreed, and that they had already formed a position on the matter:

> “[We are] in fact familiar with the NIST guidance which you are citing. While we still do recommend that passwords be changed periodically we no longer require such changes to be made on a routine basis.”

As the kids a generation ago used to say, “Boo-ya.”

Unless you’re dealing with PCI-DSS. I’d argue the above is a compensating control for their particular brand of jackassery, and would have hoped that any reasonable auditor would recognize that — did you see what I did there, using the word “reasonable” and the acronym “PCI-DSS” within 100 feet of one another? — but to paraphrase Dan, it’s hard not to suck deep, deep down when you are PCI-DSS.
