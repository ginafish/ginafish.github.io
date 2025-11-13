---
layout: page
title: User Guide
permalink: /user-guide/
---

This page was greatly inspired by

* The wonderful [Mike Craig](https://www.mkscrg.net/)'s own user manual
* "Ready To Rock: Transitioning From Engineer to Tech Leader" by Ann Yeung and Christine Sandman Stone at Grace Hopper '24

## What this is

If you've just met me - hi! This page should give you a taste of what it's like working with me. If you've known me and have worked with me, this might tell you a little more.

## My Values {#values}

* Continuous improvement
* Candor
* People
* High bandwidth communication
* Collaboration
* Variety

### What motivates me

* People
  * Working with people that I enjoy working with is more important than the work itself
* Impact
  * Knowing that I'm working on something with positive impact for my team has gotten me through tasks I thoroughly disliked - like spending 3 weeks refactoring ~20 Lambda functions that were using an outdated fork of Puppeteer just so that we could upgrade our NodeJS runtime

### Things that take my energy away

* Being siloed
  * Even if I think my work is important, if I'm the only one working on it, I struggle with motivation
* Technical projects with no clear positive business/customer outcome
  * I don't get joy out of working on technology for technology's sake. I have appreciation for cool tools, but I have more appreciation for the tool works best
* Stagnation
  * I get very frustrated dealing with the same problems and not seeing any progress or a plan for improvement

## Feedback from coworkers

* "Unflappable"
* "The one who kept things on track, but still made jokes to lighten the mood, during an incident call"
* "One thing I like about you - you're always customer focused"

## Communication {#communication}

### Methods

For long/complex thoughts: Google Doc / Notion page / etc... something that lets me comment and have discussion threads on individual ideas. No mid-conversation Slack essays, please!

For demos or detailed explanations: Loom/short video

For important or complex discussions: Zoom or phone call

For everything else: Slack! We can discuss the thing _and_ document it for future reference!

When all else fails: email .-.

### Style

I love gathering feedback on ideas, and working through problems live.

I love meeting people and getting to know them, but I do tend to be business first and social second!

### No Hello {#no-hello}

Seriously, [no hello!](https://nohello.net/en/)

> Someone: Hi! How was your weekend?
>
> Me: I had a wonderful weekend skipping through daisies. How was your weekend??
>
> _sits for a few seconds waiting for response_
>
> Someone: uh, okay. I'm really just reaching out because I want to ask about fooing the bar....
>
> Me: Oh :\( let me go find you the docs you need....

I aim to respond quickly. I almost always have notifications on, and I'll typically check my messages as soon as I get out of a meeting. If I have back to back meetings, I'm going to answer messages in order of what is most urgent.

I prefer to answer as soon as I can, even if the answer is "sorry, don't know, will try asking person X" or "I need to think on this. My gut answer is x, but I'm not sure I trust it".

If you're up front with what you need, I can get you a resolution faster (and your message will be higher priority!).

### Thoughts... so many

I try to think through things from a lot of different angles. Teammates not using new tools built for them? Too busy to test them, overwhelmed by the new functionality, or it doesn't actually do what they need? I'll knock on doors to try to get a sense of the real problem.

When I have thoughts or ideas that could be controversial or sensitive, I "test the waters" in individual 1:1's. I avoid sharing those sorts of thoughts or ideas in a group setting - until I have either social support or hard data to back the idea.

If you're my manager, if you create a space for me to speak my mind, you can expect lots of carefully placed thoughts. If you hear something that "feels off" from me, and you nudge me to elaborate, you will likely get a self-reflective and candid response.

If you're someone I collaborate with, I'll check in to see where you're at, and make sure you have what you need to succeed.

### Feedback

Giving it - I assume good intent, and focus on keeping it constructive.

Receiving it - when I make mistakes, I often beat myself up before anyone gets a chance to give me feedback. I'll likely ask for advice on how I could improve or avoid making the same mistake.

### Closing the loop

Got a technical problem that I couldn't help you with? I want to know where you landed and how you figured it out!

## Collaboration {#collaboration}

Got a system design problem you're working on? Diagrams? I love talking through ambiguous high level ideas!

### Code Review Style {#code-reviews}

* I try to leave comments noting things I like
* I'm generally 50/50 on if I test your code or just read it
  * Depends on the size/complexity/risk of the changes and quality of unit/integration tests
* If I think something is a "nice to have" that isn't worthy of making you wait >= 1 day to address, I'll prefix with "nit" or "opt(ional)". I expect "nits" to get addressed prior to merging
* If I observe few or no issues, I'll approve the MR
* If I notice something broken that's quick to fix, or I don't have a chance to do an in depth review, I'll leave comments and withhold approval
* If I notice a lot of little things, or I have a strong opinion on a change that others might disagree with, I'll just leave comments and not approve
* If I notice something significant such that I don't think the MR should be merged, I'll request changes

### Strong opinions, but herd mentality

I can be very enthusiastic and have very strong opinions, but at the end of the day, I'm going to do "whatever works best for the team", or whatever keeps the code style consistent. I'd never choose to use AWS CDK, but if 90% of the team is comfortable with it, I'll work with it. (I'll occasionally write examples in Terraform to help the team see the light...)

## Working {#working}

### Getting direction

For ambiguous problems with low direction, I'll focus on breaking the problems into components and creating high-level plans. If I have little information and I'm not able to get more, I try to gather feedback via "building the wrong thing". I have a high tolerance for thrash and changing direction based on feedback.

### Setting direction

I am always looking forward - whether it's for the next thing to work on, or figuring out the next improvement that will have the highest impact. I don't like staying in the same place or working on the same kinds of problems for a long period of time.

### Rule-minder

When I get direction that I disagree with, or that clearly isn't working out well, I'll still follow it. I'll voice disagreement in private, and I won't publicly or majorly push back. If a line is clearly drawn, I'll keep myself a yard away from it, no matter if or how much I dislike the line.

### Forward-thinking

I can absolutely take a big project, break it in to big components, and plan those components down to the minutiae. Not only do I enjoy thinking about big picture ideas, but I need some amount of that to enjoy what I'm doing. I like planning more than execution, so I'm always thinking about what is "next" after whatever I'm working on is done. The only time I stop doing that planning is when I've decided to move into a new position.

### Tolerance for squeaky wheels {#squeaky-wheels}

When it comes to things that aren't working well - people processes, software architecture, code organization, etc - I've found myself on both ends of the spectrum between "just leave it alone" and "this _has_ to be improved".

My triage criteria is:

* Do I have a clear vision of a better solution
* Are the workaround(s) causing more pain than fixing the problem
* Is there an articulable business benefit
* Is it costing the business more for this to stay the same than it would cost to change it

Something might get added to my personal backlog if it meets one of the criteria. Once a problem meets all of my criteria, I'll start pitching my solution to people, and if I hear enough agreement, I'll talk about it all the time until it gets done.

### Doing the important things

Reading my work experience, you might notice I have quite a bit of cloud infrastructure experience.

My favorite types of problems? APIs. Business logic. Data modeling. Data pipelines.

My least favorite types of problems? Networks, and root causing nebulous database failures.

UI? I can code it, but make sure I have some designs to go off of... this site uses a default theme for some good reasons!

I hate not having a full understanding of a system... which leads to me searching for root causes of problems... and draws me to the neglected-but-important pieces. I won't be the fastest coder, but I'll know where everything is, where to go to solve a problem, what works well, and what deserves some attention.
