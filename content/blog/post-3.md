---
title: "The Anti-Checklist Manifesto: Spreadsheets and 3PR"
date: 2021-10-13T15:40:24+06:00
image : "images/Excel.png"
# author
author : ["Admin"]
# categories
categories: ["lifestyle"]
tags: ["lifestyle" , "fashion"]
# meta description
description: "This is meta description"
# save as draft
draft: false
---

*Note: I spoke on this topic in September, 2021 at [44CON](https://44con.com) and you can 
[watch the video here](https://44con.com/2021/10/01/watch-the-first-44con-lunchtime-talk-with-nick-selby/).*


Third Party Risk (3PR) conversations have been center-tile on Buzzword Bingo cards for a few years now, but the way most firms approach 3PR hasn’t been effective at quantifying the risk a third-party provider actually brings to an organization. With several damaging software supply chain breaches in the course of a couple of months, executives are trying to understand how we got into this mess, and how we get out of it.

3PR methodologies vary, but they’re mainly driven by compliance or procurement teams, based on a playbook that in effect seeks to determine whether a third party service provider will introduce risk by being “less secure” or “less compliant” than the policies of the company buying the service. 

There’s a lot wrong with that assumption, beginning with the practice of handing vendors a spreadsheet groaning under the weight of baseline technology configuration questions. The idea is that companies ticking the YES box more often than not can give assurance of how “secure” or “trustworthy” the vendor is to the auditors handing out the spreadsheet. These auditors often have no information security subject matter expertise - and these days, some of the checklists themselves have been written by accountants.

We’ve thus reduced “trust” to a checklist almost entirely unrelated to trustworthiness. Rather than asking questions that highlight the risk a potential supplier might expose us to, we seem to have accepted that “trust” seems to be a product of compliance with tenets of information security configuration; ignoring that these tenets have changed significantly over the past decade as the world has moved its delivery systems from on-prem to the Cloud, and its development methodologies from Waterfall to Agile. 

A more recent gambit has been to require a System and Organization Controls (SOC) 2 Type 2 certification. SOC2 provides a highly valuable set of data in an easy to consume form, but even its creators will tell you it was never intended to serve as the sole criteria for a risk-based decision.

Here’s the story of a vendor who does things right: Their agent is written in a memory-safe language; it can only send but not receive data; in building it, all code commits must be signed by the developer with a U2F touch; all pull requests signed by the reviewer; and the source code is available for inspection by the customer. That’s just what any security-conscious customer would demand. 

A prospect recently disqualified this vendor for not having a SOC2 certification. 

A SOC 2 should start, but not decide, the conversation. It should be one consideration in assessing the risk a provider brings. 

**What Can We Trust?**

In his seminal 1984 paper, [Reflections on Trusting Trust](https://dl.acm.org/doi/pdf/10.1145/358198.358210), Ken Thompson boiled down a truism of the software world: “You can't trust code that you did not totally create yourself.”

Whether you’re just seeking to outsource what feels easiest or cheapest, or you’re formally [Wardley-Mapping](https://en.wikipedia.org/wiki/Wardley_map) to segregate the high-value core competencies of your company from commodity services you need to get to market, most companies are taking on supply-chain risk by using a lot of software as a service (SaaS). 

It is an important distinction that, “Commodity” doesn’t mean, “Unimportant.” Some commodities in the business supply-chain include real-time chat, Single-Sign On and identity store, billing, expense management, accounting, trouble ticketing, work planning, and other very sensitive things - not to mention productivity, email, and videoconference. That echo in your mind is of newscasts reporting breaches of providers in nearly all of these categories, by the by. 

All these Software as a Service offerings are the repositories in which we store our business plans, treasure maps to broken things in our organizations, confidential conversations, and, oh yes: masses of our customers’ private information. 

Learning the difference between those that were breached, and those that weren’t yet, has actually always been the point of the exercise. But none of the spreadsheet cat-rodeos surfaced the risk provided by [Zoom](https://www.ftc.gov/news-events/press-releases/2020/11/ftc-requires-zoom-enhance-its-security-practices-part-settlement), or [Citrix](https://www.fbi.gov/news/pressrel/press-releases/russian-foreign-intelligence-service-exploiting-five-publicly-known-vulnerabilities-to-compromise-us-and-allied-networks), or [SolarWinds](https://www.cisa.gov/news/2020/12/13/cisa-issues-emergency-directive-mitigate-compromise-solarwinds-orion-network), or [CodeCov](https://www.reuters.com/technology/codecov-hackers-breached-hundreds-restricted-customer-sites-sources-2021-04-19/) brought into the center of our networks. 

Thompson’s admonition is really key: the only way to view 3PR is to view it as, “If we built this service ourselves, how would we measure the risk it exposes our company to?” 

Now think of the last time you bought a SaaS product. Chances are, a business team set the deliverables, the legal team discussed the contract terms, and only after all that was done did the compliance and information security team get brought into the conversation. Odds are,  engineering wasn’t consulted at all.

Recognizing - at the level of board, C-Suite, and company management - that outsourcing commodity tasks is a strategic operational reality is very important. With recognition that the most dangerous place in any company is between the CFO and an OPEX cut, a preliminary security speed bump at the start of the bake-off can prevent those other teams from wasting their time.

If the SaaS provider can’t satisfactorily answer seven to 10 basic questions about their development and deployment pipeline, about their software development lifecycle, about their use of cryptographic proofs as attestation of authorship, their use of encryption, and the like, then here’s the thing: they either don’t know or don’t care about security enough to provide what are some very basic protections in today’s environment. 

If they fail this first gate, both sides are saved the long homeopathic consult in which we once again convince ourselves that dilution of security equals increased strength, as we wrassle with a 300-row questionnaire that neither side wants to endure. 

**So What Should We Ask?**

Unlike the spreadsheets we have been using that tell you about specific configuration, the answers to the following ten questions can help engineering and IT professionals at your company understand truly the risk this SaaS vendor brings to your business:

- Do you encrypt all customer data in transit, and at rest within your systems? 
- Does your portal support login via SAML?
- Or at the least, “Do you support non-SMS MFA?” (if they don’t do the former, they’d better do the latter)
- Does your company require its software developers and engineers accessing your own production and non-production environments to use a VPN?
- Is that VPN itself protected by SAML- Oauth, etc.- based Single Sign-on and Secure Multi-Factor Authentication?
- Do any of your internal systems use static credentials?
- How do you manage secrets in your production and non-production environments?
- Do you have a named executive responsible for security? What is their title, and to whom in the organization do they report? 
- Does your company require all engineers to undergo regular secure coding training?
- Do your engineers use a linter? Do you perform static security and dependency scanning on your codebase?

There's also one question that you can ask that can cut to the chase with the engineering team:

- Can anyone in your company use a laptop to push code to production? 

(the more polite way to ask this is, "At what level on the [SLSA Framework](https://slsa.dev/) does your company sit?")

**No Guarantees**

Getting past these questions with satisfactory answers isn’t a guarantee they’ll pass the full security audit that comes later, but it’s a good indication we’re not wasting our time continuing talks. Notice that, just as being at Level 3 on the SLSA scale isn’t an automatic qualifier, being at Level 0 is not an automatic disqualifier; in the comments the company can state where they are on their journey - maybe they’ve made a ton of progress in the past year. 

Answering “No” to more than a couple of these questions, though, means, no, we’re not going to get to your SOC certification or the spreadsheet rodeo, or read your descriptions of how you’re one of the Best Places to Work in Peoria, because your company is simply not a candidate to sell to ours.