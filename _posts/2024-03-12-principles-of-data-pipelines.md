---
layout: post
title:  "Principles of Data Pipelines"
date:   2024-03-08 21:42:05 -0500
categories: data system-scaling
---



# Terminology

*Packet* - a contained unit of data that is moving from your system. May also include metadata about itself

*Data pipeline* - a system (or chunks of code) that handle ingesting and routing data


# At what point is something a data pipeline?

Aka, when are my pants big enough to justify using big words (and better engineering tools/practices)?

Do you:
* Need to ingest data from a party not under your control?
* Need to send data to parties not under your control, or users? Multiple?
* Need to answer questions about your data beyond "how many packets did you get"?

The more "yes"es you have, the more complex your system probably needs to be. A rudimentary data pipeline that isn't being asked to do many things can likely get away with simple logging, but at some point, logging isn't enough. People who aren't engineers, or who don't have access to your logs, might need to be able to ask and answer questions about the data, and judge if the pipeline is working properly. Logging is also hard to get right when you have dozens of attributes that can control what happens to your data.


# Great, I have a data pipeline, what does it need to do?

## Where to start

It's probably safe to assume that, for any given packet, your system will need to answer the following questions:
* What, exactly, did I get?
* Where did it come from?
* Who sent it to me?
* What is in it?
* If I send it to others:
    * Who did I send it to?
    * When did I send it to them?
    * What do they want from me?
    * What, exactly, did I send?
    * Why did I send it to them?

A lot of data pipeline issues require one or more of those questions being answerable.

Think of:
* For a billing system - "Fido says he sent us a check, did we get it?"
    * You'll need to look for:
        * which checks in your system have Fido's name on them (what is in it)
        * checks that came from Fido (who sent it)
* For an email distribution system - "Alice got a Greek email, but doesn't speak Greek. Can you fix it?"
    * You'll want to look at:
        * the email that got sent to your system (what, exactly, did I get?)
        * see if your system recognized the correct language (what is in it?)
        * compare the above with Alice's preferred ingest format settings (what do they want from me)
        * check what we think we sent Alice - was it actually in Greek, or was Alice confused? (what, exactly, did I send?)


Your system needs to be able to tell you, with certainty, whether something never arrived, or if it arrived but didn't land where you wanted it to inside of your system.


## Building your index

Your index should be made up of whatever attributes your system keys off of. Think: unique identifiers, attributes that are used by routing conditionals, 

Indexing should provide what you need to answer the "what is in my packet" type questions. It should be done as a separate stage from your ingest, as it is more risky


## Normalize your data continuously

As you organize your pipeline, patterns should emerge 



## Re-process your data

Your favorite client, Bob, has a pile of papers he wants imported into his computer, and is either unwilling or unable to organize the pile so that each paper comes in the right order. Unfortunately Bob has a giant pile of cash too, so you start importing those pages into your nice paper -> computer system that will organize them for you.

The next day, you come in, and find out that some of the papers had page numbers written in Braille! Ah! Rage! You already threw the papers into the shredder!

Fortunately, your data system stored each page exactly as you imported it! But, even if you patch your system to read Braille, Bob still wants those pages.


## What is success?

Success is having data. But, if certain stages of your pipeline fail to produce a derivative of the given packet, you need to handle those failures in a way that makes sense for your needs.

Some general options:
* Quarantine the failures for later review
* Given specific conditions, have an automation step slightly tweak the packet and re-run it through the previous step
* 


# Data goes down... down... down...

"Data lake", "data pipeline", "data stream"... notice a theme?

Your packets should flow through your system like water. Rivers will fork, have sections that slow down, other that go fast and have rocks to hit, but (almost) always go in 1 single direction. If you try to enforce rules like "blue files go first, red files go last", you're going to find cases where a blue file never came in, and a red file will break your system.

Circles are okay, but be very intentional about using them. You should have a mechanism in place for handling something that is infinitely stuck, and automated processes for getting that packet back on the right track.

It's okay for your data pipeline to be a little complex. Like all software, you'll have to balance ease of development and business priorities. Make sure you keep your set of questions close at hand when updating your pipeline so that even when it drastically shifts, you 

