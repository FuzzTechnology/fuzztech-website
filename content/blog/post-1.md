---
title: "Zero Factor Authentication"
date: 2020-02-01T15:40:24+06:00
image : "images/call_center.png"
# author
author : ["Nick Selby"]
# categories
categories: ["authentication","access control","Supply Chain Risk","Best Practices"]
tags: ["authentication","access control","Supply Chain Risk","Best Practices"]
# meta description
description: "PAre you asking the right questions to determine third-party risk?"
# save as draft
draft: false
---

**Are you asking the right questions to determine how well your vendors will protect your data? Probably not.**

Let's say you own a small business, and you want to get a payroll service to help with withholding taxes and automatic deposits into your employees' accounts. That's a very useful, powerful service: You're giving a third party the right to withdraw funds from your bank account and send them to others.

Being switched on to security, you'd look for a payroll company that supports multifactor authentication (MFA) based on a time-based one-time password (TOTP) application, knowing that SMS-based two-step login is effectively (in the words of Allison Nixon and Mark D. Rasch at Unit 221B Research) [zero-factor authentication](https://labs.unit221b.com/2020/01/30/zero-factor-authentication/).

The trouble is, as of about three weeks ago, none of the major online payroll companies offered this feature. If you ask those companies, they'll say they offer SMS-based two-step login and then assure you they take security seriously.

I found one firm that does support application-based MFA: I'll call it Payroll Company B. PCB isn't a payroll company as much as a [professional employer organization](https://en.wikipedia.org/wiki/Professional_employer_organization), but still, it does payroll — for twice the price of the others I just mentioned.

Anyway, you sign up. And after you go through the rigamarole to get the TOTP application working, if you're attentive, you may discover a seedy backdoor: If you were to forget the Web front end,call PCB's toll-free support number, and tell the company you need to make an account change, the entire authentication regime falls apart with these dreaded words:

> "For security purposes, please tell me your full name and the last four digits of your Social Security number."

Yes, it verifies your identity by asking you for public information. Once provided, no further authentication is required, and you can request a password change, or the removal of TOTP-based MFA, or, presumably, to send Bob's paycheck to Alice. You're in.

And you're root because it has verified your identity. After all, who else could possibly know your full name and last four digits of your Social Security number?

Who indeed?

Without installing, for example, a proper and secure multifactor, telephone-voice-based authenticator capability, these companies are left to improvise methods to hack together a security story to offer to security-conscious customers. After I discovered its glaring password reset vulnerability, I spoke with a helpful PCB supervisor and asked him to disable phone support. He cheerfully (and genuinely) promised to do so, saying he put a note in my account. I waited two weeks, phoned back, authenticated with a different rep using just my name and last four digits of my SSN, then asked the rep to close my account. In the company's failure to fix the problem, it made liars out of dedicated and creative support staff.

#### Forget Password Policy. What's Your Password Reset Policy? ####
This vulnerability is so mind-thwackingly obvious that I cannot believe I need to say this, but it also raises an important issue that is relatively unaddressed by my colleagues in the financial services world: When we do vendor onboarding and qualify the vendor's security policies, are we asking the right questions?

Or are we sending them a 120-question spreadsheet containing lots of questions about firewall rules and antivirus? 

As a friend who is a very high-ranking financial services security leader said to me the other day, "Oh, that doesn't happen. I've never sent a spreadsheet like that in the last week ..."

This is not a theoretical issue. 

Recently, there was an attack that worked like this: The attackers had an in at a national mobile carrier and SIM-swapped the phones of some people in a targeted industry. They then used the pirated mobile numbers to call a firm that specializes in outsourced services to that industry, claimed to be the SIM-swapped employees, and requested — verbally — password resets. 

That worked, as it would have worked at PCB.

This was an attack against a third party that for many firms would have bypassed entirely the security monitoring they have in place to defend their assets. The phone was swapped at the carrier, and the password reset was done at a third party, which also set up the fraudulent transactions when the crooks logged in to that service. 

The firms that didn't fall victim to this last phase were those that did transaction anomaly detection fast enough to understand the transaction was weird.

Would your firm have caught it? 

More important, would your vendor procurement process and onboarding have asked the question, "Do you allow password resets via voice call?"

Many companies don't ask the question. I spoke with colleagues at household names in the financial services space, and many firms are struggling to catch up.

What is clear is that we are all trusting cloud-based companies more often, if not exclusively, to handle those parts of the business we seek to outsource. Looking at the standard questionnaires, I see a lot of question-types missing.

For example, rather than asking lots of questions about endpoint antivirus or whether the vendor's facility is in a location with little to no risk of natural disaster, terrorism, or civil unrest, it might be good to ask whether the vendor has separate production and nonproduction environments, or how their admins and developers access the environments, or how customer password resets are done.

In other words, we need to ask questions designed to understand the ways someone could subvert the vendor's authentication and access control regime.