---
layout: post
title:  "The Value of a Project Pre-Mortem"
date:   2024-04-14 19:42:05 -0400
categories: software-decision-making
tags: software-lifecycle project-planning
---

## What is a pre-mortem?

You have an idea, a documented set of requirements, and a technical implementation plan. You're ready to kick this project off!

Are you? What if there's something that you've overlooked that could mean the death of the project, even if you have a completely rock solid plan?

The goal of a pre-mortem is to try to suss out things that could cause a project to fail before starting the project. It's a designated space for teammates to air out hunches that they have, and do a final check on if anything was missed in the planning thus far. Talking through failure scenarios helps you QA what you have planned out before you start executing it, which is cheaper than QA'ing it afterwards!

## When does it make sense to do a pre-mortem?

Consider if any of the following criteria apply to your project:

* It's big
* Planning thus far has been very "top down driven" (people executing the project haven't had much say on the project scope or deadline)
* Doesn't have full alignment from everyone involved on the goal(s) of the project
* The outcome of the project is very reliant on the actions of a third party
* Feels "risky"

If any, or many, of the above apply, then a pre-mortem might be right for you!

If you decide to do one, you'll want to schedule the meeting before starting the project, and after you've wrapped up planning for the project. When you've already started executing the project, it's more painful and requires more context switching to go back and assess if your plan is good. You want to make sure that the planning is done first for people to have a basis for the discussion.

## What do you get out of it?

Sometimes, the only thing you get out of the pre-mortem is people feeling more confident about the project. This doesn't mean that the meeting was a waste of time - making sure that everyone is aligned on the goals and implementation plan means that they can go straight into implementing the project without having to spend time thinking over "what's left". It can also be a great way sanity check as to what peoples' roles and responsibilities towards the project are, and help avoid painful "I thought you owned keeping this working because you did the project wrap-up" conversations.

Some things you should try to get out of the meeting are:

**Questioning the project scope** - is the project scope too broad? Too optimistic given its deadline? Or is there something missing that would exponentially improve the user experience?

**Evaluating the resources available** - does the project actually have everything it needs to accomplish what it should by its completion date?

**Contingency planning** - have you discovered everything that could go wrong? Are there any blind corners that you can't see around, and are there sufficient precautions to handle something nasty that jumps out? Are there any checkpoints you can set up during implementation that would allow you to validate assumptions or hunches before you have problems or waste resources?

**Evaluating outcomes** - do you have the proper metrics in place to evaluate if you were successful? Are you prepared for project failure _and_ success? Could you be more successful than you were built to handle? And, even if the project failed, was there something built that can be re-used later?

## Structure of a pre-mortem

### The template

[Atlassian](https://www.atlassian.com/team-playbook/plays/pre-mortem) has a pretty good set of templates to start with!

Make sure you include both "good" and "bad" prompts. The "good" prompts help you keep in mind what contingency plans you already have, so when you start working through "worst case" scenarios, you can more easily redirect the conversation or alleviate fears. The meeting is for proactive planning, and you want to have a structure that keeps people from going down a negative spiral.

Once you've decided on the template and prompts, put it on a board that you can share with your teammates. If you want, you can also add some ideas yourself ahead of time, to both help the meeting go faster and give people some ideas for inspiration.

### Running the meeting

Your project failed. Start brainstorming why!

Start by giving folks time and space to think, and add items to the board asynchronously. Expect people to add things in bursts. It can be difficult to tell the difference between a lull and people genuinely running out of ideas, so set a timer for at least 5 minutes, and only end it early if no one has added anything in a minute. People might use this time for reviewing what other people have added as well.

Next, go through everyone's suggestions. If you noticed multiple items with the same theme, try to group them together. If you have more items than time, add a quick step of having people vote for a few items they want to talk through.

Go through the items nominated for discussion. For each item, ask the writer to read their item, or expand on what they wrote, then discuss the likelihood or benefits of the item needing addressed and evaluate if there is already something in your contingency plan that should help. If discussion on a particular item drags, create an action item for following up on it later, even if that action item is just further research or discussion.

If an item is should be addressed (likely to become a problem, or the benefits are worth the added scope), create an action item for addressing it.

Try to make sure that the meeting is at least somewhat fun! You want peoples' creative juices flowing here, and you want it to be a safe space for people to bring up things like "I'm worried this project won't be successful because I don't know xyz well enough".

### Wrapping up

Go through your action items and ensure that they all have assigned owners. Try to also ballpark the priority and complexity of the action item - moderate impact items that need a complex mitigation solution might not be worth prioritizing for a minimum viable product, but would for a very polished product with picky users. Feel free to start async discussion threads on your favorite communication platform for any items that need more detailed mitigation strategies, or figure out other stakeholders that should be involved in follow-on discussions.

And then, you can jump right into implementing your project feeling good about what you have planned!
