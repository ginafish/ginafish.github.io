---
layout: post
title:  "Principles of Data Pipelines"
date:   2024-03-25 22:26:05 -0400
categories: data system-scaling
---



## Terminology

*Packet* - a contained unit of data that is moving from your system. May also include metadata about itself

*Data pipeline* - a system (or chunks of code) that handle ingesting and routing data

*Data* - a blob of bytes

*Metadata* - facts that tell you things about a piece of data, while in and of themselves also being data

## At what point is something a data pipeline?

Aka, when are my pants big enough to justify using big words (and better engineering tools/practices)?

Do you:

* Need to ingest data from a party not under your control?
* Need to send data to parties not under your control, or users? Multiple?
* Need to answer questions about your data beyond "how many packets did you get"?

The more "yes"es you have, the more complex your system probably needs to be. A rudimentary data pipeline that isn't being asked to do many things can likely get away with simple logging, but at some point, logging isn't enough. People who aren't engineers, or who don't have access to your logs, might need to be able to ask and answer questions about the data, and judge if the pipeline is working properly. Logging is also hard to get right when you have dozens of attributes that can control what happens to your data.

## Great, I have a data pipeline, what does it need to do?

### Where to start

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

A lot of data pipeline issues can't be addressed unless one or more of those questions are answerable.

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

### Building your index

Your index should be made up of whatever attributes your system keys off of. Think: unique identifiers, attributes that are used by routing conditionals, and literally anything you might want to search. Ideally, anything downstream of this step should not need to touch the original raw data.

Indexing should provide what you need to answer the "what is in my packet" type questions. It should be done as a separate stage from your ingest, as you don't want a indexing failure cause an ingest failure.

### Normalize your data continuously

As you organize your pipeline, patterns should emerge in what tasks your pipeline needs to do.

Be very wary of wide fans and wide conditionals. The straighter and more vertical your pipeline is, the easier it will be to understand. It's often better to have a chain of "if x do y, else noop" than "if x do y, else if z do c". It also allows you to evolve your packets over time, as you learn more lessons and better understand the packet you received, and how it relates to other packets in your system.

Normalizing isn't always necessary - generally only relevant when ingesting data from multiple sources, or sending it to multiple consumers - but doing it right means vastly less complexity in your system.

Take, for example, you have 1 source sending you JSON, and 1 sending you YML. Both contain data for family trees. If you parse out the data for `children` in each, and leave that data in the same format as it came in as, anything that wants to work with `children` has to support YML and JSON both. If you make a decision on which format you prefer, and just transform the YML into JSON before saving it on `children`, you avoid that problem. While that does require you to know in detail what the shape of the incoming data is to be able to index it, so does anything downstream of the index, so you save piles of additional complexity just by doing the normalization. If the normalization fails, you know that the shape of the data changed, and can apply appropriate error handling.

If you do have a consumer who prefers YML over JSON, you can just later normalize *all* of your packets into YML, and send them the result of that transformation. You can either do that normalization just for the data that you send that consumer, or for all of your data, if you think you might have other consumers interested in the same data format. Don't forget you can keep multiple copies of the same packet, and tie those packets together via a unique identifier.

### Re-process your data

Your favorite client, Bob, has a pile of papers he wants imported into his computer, and is either unwilling or unable to organize the pile so that each paper comes in the right order. Unfortunately Bob has a giant pile of cash too, so you start importing those pages into your nice paper -> computer system that will organize them for you.

The next day, you come in, and find out that some of the papers had page numbers written in Braille! Ah! Rage! You already threw the papers into the shredder!

Fortunately, your data system stored each page exactly as you imported it! But, even if you patch your system to read Braille, Bob still wants those pages.

### What is success?

Success is having data come in, and data come out. Sometimes, your packet may not have the data that you want, and you might want to make the packet fail. If certain stages of your pipeline completely fail to produce a derivative of the given packet, you need to handle those failures in a way that makes sense for your needs.

Some general options:

* Quarantine the failures for later review and re-processing
* Given specific conditions, have an automation step tweak the packet's attributes and re-run it through the previous step
* Let your packet skip past the step that failed (no-op)

## Data goes down... down... down\.\.\.  <! -- markdownlint-disable-line -->

"Data lake", "data pipeline", "data stream"... notice a theme?

Your packets should flow through your system like water. Rivers will fork, have sections that slow down, other that go fast and have rocks to hit, but (almost) always go in 1 single direction. If you try to enforce rules like "blue files go first, red files go last", you're going to find cases where a blue file never came in, and a red file will break your system.

Circles are okay, but be very intentional about using them. You should have a mechanism in place for handling something that is infinitely stuck, and automated processes for getting that packet back on the right track.

It's okay for your data pipeline to be a little complex. Like all software, you'll have to balance ease of development and business/feature priorities.

## What if you have packets that relate to each other?

If you have two packets that cannot be handled successfully without joining the context of the two together, you have a fun dependency issue.

Here's some general strategies for managing it:

* Refuse to ingest the first one until you're sure you have the second one
* Ingest the first, put it in a holding queue until either the second arrives, or you hit a timeout
* Get each as far long as possible, handled separately, and then have each look for the other. If one can't find the other, have it stop, and assume the second will find the first.

And always keep in mind: no matter how sure you are that the order of in which each file will come in will always stay the same, the universe is spiteful and will make sure that you get new creative and unique problems.
