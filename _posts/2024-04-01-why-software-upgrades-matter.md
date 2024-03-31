---
layout: post
title:  "Why Software Upgrades Matter to Your Business"
date:   2024-03-31 20:26:05 -0400
categories: software-decision-making
tags: technical-mumbo-jumbo-to-business-impact software-lifecycle risk-management
---

Software upgrades are an important part of maintaining a software system. However, it can be difficult to quantify their impact on a business, and it's easy for them to be ignored... but only for so long.

It's like paying your taxes - if you don't do it, you will get audited. If you're using open source software, remember that it isn't free.

This walks through two extreme scenarios that won't be relevant to most organizations, but should be kept in mind by anyone who is managing engineering resources. If you do genuinely refuse to allocate time for doing software upgrades within your organization, these scenarios will happen - it's just a question of when.

## Worst Case Scenarios

If you have avoided upgrading your software for as long as possible (understandable - upgrades often aren't fun, and don't directly relate to business needs), there are two realistic cases that you should be aware of.

1. Your software will cease to function if you do not upgrade
2. A piece of technology you're using has a 0 day vulnerability discovered

One of these two cases will inevitably happen if you don't do updates (and, often, even if you do do them).

### Wait, is it true my software won't work? Actually not work, or just not work well?

Genuinely not work. Especially if you are reliant on cloud services or open source technologies.

[AWS will regularly deprecate](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html#runtime-support-policy) older "runtimes" (think "operating system for code") of their services. AWS does this because it's a lot of work on their end to keep old runtimes available - often those runtimes are open source technologies, and the people who actually create the services will not support them anymore. AWS has no incentive to keep really old runtimes available for your use, so try to force you to upgrade.

Depending on the specific technology and your vendor choices, your technology may still work, for a time. Your vendor might make it so you can't make updates to your software without upgrading, and if you don't ever update that piece of technology anyways, you won't mind that restriction... until you have an emergency and do need to patch it.

How AWS handles deprecating runtimes is actually pretty generous! Other infrastructure tools you might use, like CircleCI, will [prevent you from using their servics](https://discuss.circleci.com/t/remote-docker-image-deprecations-and-eol-for-2024/50176) unless you upgrade.

### Why should I care about vulnerabilities?

If you want your business to reap the benefits of technology, you need to manage the downsides of technology too.

If your business is in a regulated industry, the fines for failure can be business ending.

Even if your business isn't in a regulated industry, you might be signing contracts with people who require you to meet certain compliance standards, and they won't be happy if you risk their business because you don't meet them. Keeping your software systems up to date is part of every compliance standard.

0 day vulnerabilities at organizations that refuse to do upgrades are a goldmine for nefarious people! There is an entire industry of people who go around looking for good targets, and if they find a vulnerability in your system, you bet that you'll be on a list that they sell to someone who will exploit that vulnerability.

## Why it's more work to wait until you're forced to upgrade

You haven't done any software upgrades in months, but your business is still afloat and your technology is still working as intended. It sure seems like there's no negative consequences from just waiting to do the upgrades until you're forced to, right?

A software system is a web of interconnected pieces. It is very common that if you want to upgrade one thing, that cascades into needing to upgrade several things.

If you're lucky, people who did the same upgrade years ago will have posted the steps they had to take somewhere on the internet. If you're not, you'll be navigating complex dependency graphs, trying to figure out problems like "my banana is only available starting version 2.3.1, but my toast stopped getting updates and needs version 2.0.1 to still work! Do I have to swap toast for an apple?"

Doing upgrades proactively lets you avoid worst case scenarios, and make the process of doing the upgrade itself easier. If you had upgraded to the latest toast version when it was available, you could have been able to get your banana upgraded, but now that you've missed that window, you have to do a lot more work to get your banana upgraded. You would have needed to do that work eventually, but now you have an incident forcing that upgrade, and can't spend as much time evaluating apple vs toast because now you're doing the upgrade just to be able to continue doing business.

## Are there any upsides?

Yes! Software upgrades aren't just for fixing security issues - you can get both performance upgrades and new tools from upgrades. New tools can help accelerate your software shipping speed!

## How bad can it be? Some famous real world issues caused by companies refusing to do upgrades

Other people did this post better - [here's 10 examples](https://www.1e.com/blogs/10-unpatched-software-security-breaches/). Most of those companies are still around, but had to deal with expensive lawsuits due to their breaches, and/or pay a ransom to hackers.

[Cybersecurity insurance is a thing](https://www.ftc.gov/business-guidance/small-businesses/cybersecurity/cyber-insurance), but you can bet an insurer will charge you more if you don't do your software updates.

## How this should factor in when you decide to add a new piece of technology

Keep in mind:

* Does the producer of that technology write guides for 0 downtime upgrades?
* How frequently does that technology get updates? (Doing it too often or too little can be an issue)
* Do you have a sense of how many resources you need to ensure an upgrade gets done?
* Do you have a process that gets you to install upgrades at a regular cadence?
* If open source:
  * Is there a strong official backer who has a vested interest in patching that technology, or is it all generous volunteers?
    * Is there a chance that the [backer will try to commercialize that technology](https://www.infoworld.com/article/3714743/redis-moves-to-source-available-licenses.html)?

Every new piece of technology you add will increase the number of upgrades you need to do, so if you add something, make sure it's worth it!
