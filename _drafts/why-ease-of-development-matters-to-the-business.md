---
layout: post
title:  "Why Business Leaders Should Care About Ease of Development"
categories: business crossfunctionalengineering productengineering
---


Engineers aren't famous for their communication skills. That could be its own post. (Neither are they unique in having that challenge....) But, generally, engineers are pretty well-meaning people.

## What does a developer mean when they talk about tech debt?

One of the big promises of software engineering is automation. You write something once, and it takes away hundreds to millions of monotonous tasks from a human being, freeing them to do something that requires more thought or creativity.

When that expectation of automation breaks down, it's frustrating. People are complex, and software is naive. You ask the software something it didn't expect, and it breaks down. The more you ask from your software, the more breakdowns you'll find.

## So, why are my engineers talking about "tech debt" when we have things that need built?

Building something from scratch is fun. Developers will do this in their free time, and it's one of the reasons why there is so much open source software.

Adding something to an existing system is stressful. You're working on a giant Jenga tower that you don't have a lot of visibility into. There may be scaffolding around the tower, but it's so high up in the clouds that you can't see more than a few feet in front of you. You can add more scaffolding, or get some brighter lights, but if there are blocks far below that are missing or falling apart, you might not notice until it's too late.

Scaling software, and building complex systems, is about keeping that tower upright as you throw new blocks on top.

At some point, keeping that tower upright takes so much work, you don't have any energy left to throw new things on top. Even though building new blocks is the _fun_ thing, keeping the tower upright is the _important_ thing. If you can't keep existing customers, you won't be able to keep new ones.

## The value of developer speed

Given that complexity builds as you build more things, if you don't make time for reducing complexity as well, at some point, developers are going to slow down. Slower developers produce less widgets to sell.

"Can't they just ignore it?" Not if they have to keep it from breaking when they change something next to it. A good test suite helps uncover when a change might break something, but some things are just inherently untestable. If your organization has a perfect test suite, your organization is also likely not having to worry about tech debt.

## What does "tech debt" mean in reality?

Ask your engineers. Lots of tech debt causes real negative user experiences. If it doesn't, does it make your software harder to maintain, and thus slow down your engineers?

## Some essential reading for people who work directly with engineers

If you have never been an engineer, it can be hard to understand what your engineers are saying. It's easy to mistrust complicated things that you don't fully understand, and building software can be akin to complex research, so engineers have to stop and translate "jargon" into human terms in a very literal way, while having to jam the explanation into one quick 15 minute meeting with a business leader. Just the same as a doctor needing to explain what a prescription does to your "lymphatic system", an engineer needs to translate how computer bytes relate to you as a person.

Doing that translation requires a lot of patience. It also requires a lot of patience to sit through someone doing that translation. It takes a lot of trust on both sides to have that patience.

Technology and health are both part of your every day life. Here are some things to read to help meet your engineers where they are at:

* Things to keep in mind when using open source technology
  * [The Leftpad incident that broke the internet](https://www.theverge.com/2016/3/24/11300840/how-an-irate-developer-briefly-broke-javascript)
  * [Log4j](https://www.ncsc.gov.uk/information/log4j-vulnerability-what-everyone-needs-to-know)
  * [Why open source isn't free](https://www.ibm.com/blog/why-open-source-isnt-free-support-as-a-best-practice/)

