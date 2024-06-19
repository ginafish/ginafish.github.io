---
layout: post
title:  "Alerts, alarms, and noise"
categories: crossfunctionalengineering
---

An alert comes in - "unhandled exception, foobar, @Engineer"

Engineer takes a look. After a few minutes of looking at it, they assess the alert to be one of the following:

* Urgent - an important user workflow is affected
* Bug - Something is broken, but it doesn't require an urgent fix
* Unknown - Could be a bug, but if it is, it's difficult to reproduce, or has little user impact
* A false alarm

If the alert indicates an urgent issue, the engineer will start trying to fix it. They may pull in other engineers to assist.

If the alert was just a false alarm, the engineer will either mute the alert, or make a code change to prevent whatever triggered the alert from doing so again.

For the other two cases, the engineer creates a ticket with their findings, and places it in the appropriate teams' triage queue, allowing product team members to prioritize the bug against all of the other ongoing priorities. Ideally, the alert is silenced so that it doesn't ping the team again, but is left around so that if it becomes a bigger or more common issue, the team can re-prioritize fixing it.

This is what a healthy alert system looks like.


## If a tree falls in a forest, does it make a noise?

Alerts are one of many tools that engineers use to ensure that an application is working as intended. They are *only* useful when they occur in *small* doses.

Alerts that go off, and don't trigger an action, are just metrics. Very noisy metrics.

A forest is full of trees. If you see smoke everywhere, you don't know if you have a few campfires, or one big wildfire. Alerts are there to help you catch fires before they become wildfires.


## I have an alert system that feels manageable. What should I do to keep it that way?

Keep the volume low, and accountability high.

For smaller teams/companies, you should have a process that calls out a specific person, or two, as the alert triager. They should spend no more than a few minutes per alert each day, and they will be responsible for keeping the alert volume at a manageable level.

Two people is (almost) always better than one, and they can help keep each other accountable, and make the work feel less lonely. If your alert system got into a mess, it was because no one felt accountability over keeping it clean, or found value in doing so. There are people that thrive doing bug fix work. Even still, if that work isn't acknowledged, it can feel meaningless.

If you're a teammate who is responsible for setting the team priorities, make sure you prioritize alert resolution work when it comes up. If you don't consistently do it, you are giving your team signals that resolving alerts isn't valued work, and they will stop spending time on it.

Identify what a manageable threshold looks like for your team. If your team struggles to maintain that threshold, it can be a sign that you are close to a tipping point. Once you cross that tipping point, inertia sets in. Nobody triages alerts because there are dozens, rather than a handful. Why bother taking the time to look into a couple of them? And the worse the volume gets, the more work it takes to dig yourself out of the hole.

Build a culture of pro-activeness. Make sure people understand why the maintaining status quo is important. Stomping out a fire takes more effort than pinching a few sparks.


## I have a forest, but I'm having trouble justifying getting the dead leaves raked up

Acknowledging that you have a problem is the first step!

Go treasure hunting in your alerts channel! If it is truly in a state of neglect, you should be able to find some examples of tragically poor user experiences, or milder negative user experiences that have been ongoing for a long time. You want something that would be a "no brainer, needs fixed" that has been costing the company money for a while. Then, remind people that there could be more such issues!

If your organization cares about company morale, you can point out that having alarms go off all of the time is very stressful, and leads people to believe that your product is full of nothing but bugs.


## Cleanup

Look at your noisiest alerts first. Not the ones that affect the most users, or create the worst user experiences.

By getting rid of the noisiest alerts, you move the team much more close to the ideal experience sooner. Your product will never be bug free. The motivation of your team should be to *minimize* bugs and their impact.

Only once you have decreased the noise should you focus on prioritizing alerts by customer impact. The point of alerts is to ensure good user experiences, and you are a user of your alerts!
