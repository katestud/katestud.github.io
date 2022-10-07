---
layout: post
title:  strangeloop
date:   2022-09-29 15:34:03 -0400
categories: "conference notes"
---

Last week, I attended [Strange Loop 2022](https://www.thestrangeloop.com/) in
St. Louis. I've been wanting to go to this conference for quite some time, as
many friends, mentors, and others, have sung its praises. Apparently, 2023 will
be the final year of the conference, so I'm glad I was able to make it this year!

Some musings / ramblings / resources / notes from my time there follow.

* I attended an interesting workshop on the new [Block Protocol](https://blockprotocol.org/workshop),
where we were tasked with building a block and modifying it. The Block Protocol
aims to develop a standard for interactive UI elements. We learned a bit about
the API, how blocks communicate with applications. My main takeaway was that it
seems like it'd be difficult to find the right abstraction to design a block
that has enough specific behavior that reaching for a block rather than
reimplementing the behavior is worth it, while not making the behavior _too_
specific to any one application.
* The Tackling Technical Debt workshop by [Chelsea Troy](https://chelseatroy.com/)
was interesting. I was hoping that the workshop would go into specifics about
tooling and methodologies for _quantifying_ the amount of technical debt in a
codebase, but I found that this talk focused more on _types_ of debt and which
to prioritize. Some interesting takeaways:
  * Technical debt is measured in terms of maintenance load in an existing codebase
  which comes from context loss.
  * Companies tend to think about code as an asset and developers as costs, so
  quantifying maintenance load in terms of "units of developers" can help leaders
  understand how debt should be prioritized.
  * Signs that your maintenance load is not under control: there are agreements
  to "take on" technical debt to deliver a product, team accepts that some
  features just don't work, or there are entire areas of your codebase that
  teams avoid working in.
  * Ways to reduce tech debt: Write discoverable code, add flexibility and
  rigidity in the right places, document code with detail, tests should convey
  functionality and boundaries, and context should be transferred to other
  members of the team through pairing, PRs, documentation.
  * Rather than making code flexible everywhere, think about where changes are
  likely to be made.
  * Watch out for pet refactors -- these erase context and they don't reduce
  maintenance load.
  * When prioritizing tech debt, focus on items in these areas, in this order.
  Higher impact items at the top:
    * Remove feature bloat -- delete features that aren't serving constituents
    of the product. If you need justification to do so, focus on where maintaining
    is preventing you from adding new features.
    * Address documented holdups that frequently blow up time estimates. You can
    find these in retro notes, or areas that devs repeatedly complain about.
    * Address "abandoned houses" when changes are needed. Reward devs for forensic
    analysis in areas where things are hard to change or abandoned.
    * Look for areas where code flexibility doesn't match how often the code changes.
    * Equip engineers to suggest streamlining options (areas where simplifications
    could be made)
* Marian Petre's [Expert Software Developers' Approach to Error](https://www.thestrangeloop.com/2022/expert-software-developers-approach-to-error.html) was particularly powerful and empowering for me. Her research found that experts and high performing team tend to see error as an opportunity, reflect on the problem, and have pragmatic strategies for dealing with errors: either tolerating, deferring, or compromising. High performing teams tend to:
  * drive conversations back to purpose -- what are we looking to accomplish?
  * make things simpler, focus on what they'll be able to demo in short iterations
  * focus on what they're looking to achieve, not focused on metrics -- "Accuracy of measurement tends to get confused with relevance of measurement, much more than most people believe" -- Richard Hamming
* Following Marian's keynote, I attended a mini conference called "It will never work in theory". This was a series of lightning talks from software researchers, focused on different tooling for mitigating APIs, fixing software errors, etc. Some points from these sessions:
  * Fostering learning on software teams is critically important. Don't fall for the inspirational posters on the wall -- if team members get feedback that learning isn't important or that certain types of mistakes are not okay, they'll retreat to learning behind closed doors. Encourage pair programming, leaders on teams should follow the "best practices" they espouse, and code review should be an opportunity to educate and learn, not to penalize.
  * Chris Brown's research focused on how to get developers to use new tools in their workflow. As expected, developers generally don't want to try new tools and many methods for encouraging them don't work. Their research focused on nudge theory as the most effective way to get developers to use tools (they also referenced dependabot as a good example of this). Developers generally prefer tools when their use is frictionless -- instead of a PR comment, make a suggested code change. Another (somewhat) effective way for developers to pick up new tools is seeing a tool in use during a pair programming session.
* [Remember when we broke the internet](https://bit.ly/breaking-the-internet) was a fun history of open source software and how big events (like The Morris Worm, Heartbleed, and left-pad) shifted the landscape significantly. This talk included an audience singalong to a parody of "We didn't start the fire." 😺 This talk was a call to action to the attendees to contribute back to open source (but not in the way that you'd expect). First, the glue work in open source is critically important to open source's success, but it's not valued or recognized as much as it should be. And, we need to tell the untold narratives around open source and be more transparent about how open source decisions get made.
* Building Observability for 99% Developers by Jean Yang focused on how the majority of developers are not the ones that work at "big tech companies" and have vastly different needs when it comes to understanding their software. They need systems that allow for "one-click" observability which can observe their systems without any (or with minimal) configuration. I enjoyed this talk a lot because Jean has an academic background and shared her journey from believing that types could save the world to understanding the real, messy world of software development where we debug with print statements, test in production, have an ever expanding set of APIs and microservices.
* [A Commerce-centric Approach to Queuing Fairly at High Throughput](https://www.youtube.com/watch?v=J3uUpEC_K78) was an interesting deep dive into how Shopify updated their queueing logic to handle flash sales. What I thought was most interesting was how they verified the new queueing system was able to work at production-scale. I didn't take great notes during this session, but I'll probably rewatch the talk at some point. 😺

Resources:

* [Art of Documentation](https://chelseatroy.com/2021/09/14/the-art-of-documentation/)
from Chelsea Troy
* [Software Design Decoded: 66 Ways Experts Think](https://mitpress.mit.edu/9780262035187/software-design-decoded/) by Marian Petre and André van der Hoek
* ["It's like coding in the Dark"](https://www.catharsisinsight.com/_files/ugd/fce7f8_2a41aa82670f4f08a3e403d196bcc341.pdf) by Dr. Catherine Hicks
* [Developer Behavior Research](https://code-world-no-blanket.github.io/research/behavior.html) from the Code World Lab
* [Remember when we broke the internet slides](https://bit.ly/breaking-the-internet) from Julia Ferraioli and Amanda Casari
