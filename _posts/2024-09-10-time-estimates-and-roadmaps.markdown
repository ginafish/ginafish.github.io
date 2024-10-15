---
layout: post
title:  "Time estimates, and how they work with your roadmap"
date:   2024-10-14 19:42:05 -4
categories: software-decision-making
tags: software-lifecycle project-planning crossfunctionalengineering risk-management
---

Coming up things that are worthy of doing is one challenge, and figuring out which things make the most sense to do is another.

Planning a roadmap for a software development team means taking lots of ideas, balancing the concerns of many different stakeholders, figuring out how to most effectively make improvements in the least amount of work, and deciding which things should be done when.

When your roadmap is filled to the brim, it's easy to get into a state where everything is important, and urgent, needing done as soon as humanly possible. It also begets misuse of a certain tool: the time estimate.


## TL;DR?

A time estimate is an _estimation_ of how long something will take to do.

It is not a deadline. It is merely a tool, and should not be the first factor you consider for a project.


## What do I do when I have an idea?

### Understand the value you hope to create _deeply_

Consider this: a widget excitedly requested by a customer with a large social media and lots of capital to spend.

An excited high value customer? Great, let's start building! Excited customers tend to spend money, right?

Pause. Take a deep breath. That _isn't enough_ information to use to put something on your company roadmap!

* How many other users do you expect this would excite, as a percentage of your existing user base?
* What new value will you create by doing this for this customer? Are they already excited and going to stay anyways, or are they disgruntled and considering using another product?
* Will this widget attract new users? How many, compared to the size of your current user base?
* Would users in general be excited enough to spend money just to use the new widget?

There are a lot of things that should be hedged when deciding if one project is worth doing over another. If you don't understand these things, then you can't accurately assess if the project is worth spending time on!

You have time estimates _because_ you, theoretically, have many ideas worth spending peoples' time (and thus money) on. You need time *and* value estimates to understand the _value you're creating_ and the _value you're spending_. If you don't understand both those things, you can't appropriately prioritize all of the things on your company's roadmap.


#### I have a great idea that I've invested a lot of company resources into, and if we just do ooone more thing...

This is exactly the place for comparing time estimates against value estimates.

May that one additional thing push a feature over the edge to be an "app-killer"? Or are you continuously building something, and hoping that you're right around the corner from "something"?

If you've already spent a lot of time on something, and you haven't gotten the value you've expected from it, it can be time to give it a rest. Put the widget aside, and go try to learn your customers' wants and needs better! Give your experiments time to simmer. Don't over-invest in things that don't show much return (also good financial advice?).


### Define your real goal

Going back to the example above, don't set a company goal based on something that simple.

BAD goal: Jimbob wants to see prettier colors on our dashboard, we should do what he asks.

BETTER goal: Jimbob brings in 50% of our revenue, and he's colorblind, and is struggling to use our dashboard. We should make our dashboard more accessible.

There should be:
* A defined problem (_not_ a solution)
* A weight of impact
* Insight beyond the surface problem - looking around the corner from the initial proposal

Jimbob's problem is important not just because of how much revenue he brings, but also because he is unlikely to be the only colorblind and value-bringing customer. It also reads more into Jimbob's problem than what he'd described.

Users don't always know what they need. They can only tell you what they want.

By defining the problem better, beyond what Jimbob wanted, you can keep your focus on solving it, and not get stuck building an insufficient solution just for its own sake. You might later find out that Janice, who brings in 25% of the company's revenue, is struggling to navigate the dashboard because of her arthritis... and thus you can potentially solve two problems at one time!

Describing the weight of impact helps you better prioritize the problem. Helping out colorblind Jimbob would be less important if he was only bringing in $2 a month. Problems are everywhere. The goal of roadmap planning is finding the _right_ ones to try to solve!

Good ideas often have many reasons why they should be executed on, not just one.


### Acknowledge the risks and complexity

Things rarely will go to plan. If they do, you probably weren't ambitious enough.

You can account for this uncertainty by giving a separate risk and complexity estimate, and not building it directly into your time estimate.

If you are regularly struggling to account for want to help build an understanding of how high complexity objects can spiral deadlines, use the complexity as a modifier for your time estimate.

Ex: I have a gut instinct that this feature can be done in 14 days

* Low complexity: 1.2x
* Medium complexity: 1.8x
* High complexity: 2.2x

Applying those multipliers to the gut estimate...

* Low complexity: 14-17 days
* Medium complexity: 14-25 days
* High complexity: 14-31 days

Because you communicate those estimates separately, you can have a more honest conversation with your team about whether a project is on track or not. Expect the best, and plan for the worst!

Complexity can also help account for when a solution didn't fulfill a goal as initially planned. Maybe you didn't understand a problem well enough, and needed to re-implement something? That shouldn't be treated the same as when engineers are "just plain building too slow".

They can also help you understand when a project is really on track or not. If you're 10 days into a low complexity project, and only halfway done, then you can see if giving the team more resources would help. If the project is highly complex, then being 10 days in and halfway done is good news!

That does mean that your roadmap has to be somewhat fluid. Scheduling projects so that their timelines are variable, but not overlapping, can be a challenge. However, consider that your projects "always going over estimate" is also challenging to schedule around, and making people feel demoralized because they're not meeting "deadlines" doesn't build velocity!


### Don't abuse the deadline

How much time something takes to build is a huge factor in determining if something should be built. It's useful to track how much time a project is taking and compare it with the original estimate.

Pointless deadlines create pointless stress.

A deadline is not a time estimate. You do not set a deadline based on a time estimate.

I've worked on a project over a weekend to get it completely done by a deadline, only for the PM to cancel the project instead of launching it.

Deadlines are useful when:
* Working with third parties, and contracts
  * People lie, intentionally or not. I've seen supposedly motivated partners lose momentum and fall behind deadlines. Contract deadlines help you when your partners don't seem to want to ever complete their side of the deal, or when they've misled you with their estimates
* They are event based, such as wanting your new whale camera done by the time you go to the whale watching convention

Both examples involve something that isn't completely in your control, and is unlikely or extremely difficult to change.

Deadlines are not useful when imposed internally, set entirely based off of a time estimate, just so that you can say you got a project done on time. They are only useful when there are real consequences for not meeting them. However, keep in mind that they are generally negotiable, often slide, and frequently undermined by being naturally arbitrary.

Time estimates and deadlines should only be used together when deciding if the *deadline* is reasonable - not when deciding if the time estimate is reasonable. 


### Don't marry your time estimate

A time estimate is _just_ an estimate. You need them because you need to be able to communicate with stakeholders, and allow them to make plans around your plans.

There are times where a time estimate will sway when, or if, you should do something. These cases will be when there's a mismatch in the impact of your project and the amount of time something will take! It's impossible to judge either side, or decide which trade-offs are worth it, without both major pieces.

Given that you need to make those judgement calls with imprecise estimates, you need to be able to be honest about the fact that they're imprecise!

The time estimate is a starting place for discussion. You can't negotiate with it without making it even more inaccurate. What you can discuss is the things making up the time estimate, and figuring out if you need them in order to reach your end goal!


## What's the point?

The point of time estimates are to ensure you are spending resources wisely compared to the value you're going to create.

You should be planning your roadmap based on a blending of:
* Goals
* Expected value
* Costs
  * Time estimates (time is $$$)
  * Budget (actual $)
* Risk/Complexity
* Deadlines

Creating value can be a goal... but not a very good one. (Your goals should be [SMART](https://www.atlassian.com/blog/productivity/how-to-write-smart-goals).)

Only by blending all attributes together can you plan your projects well. If a goal is taking longer to meet than estimated, but is still expected to create more value than you've spent, it might still be worth the time. If a goal is completed, but in less time than estimated, or it created less value than estimated, it's still complete and you should move on. You might also want to change an individual goal to cut scope if the value is low or costs are high, or add scope if the costs are low and you think you can create exponentially more value.

Projects that have high costs (time, budget) compared to value should be prioritized behind projects that have a better cost:value ratio.

Not everyone will agree on time or value estimates. Acknowledge that they aren't perfect, and try to get people to agree that they are _reasonable enough_ estimates for the sake of setting priorities.  People not agreeing on priorities creates fractured teams who are chasing towards too many goals and not effective.

