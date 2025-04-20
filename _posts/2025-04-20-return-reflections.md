---
layout: post
title:  "return reflections"
date:   2025-04-20 10:34:03 -0400
categories: "rc"
---

Attendees of the [Recurse Center](https://www.recurse.com/) follow a tradition of
writing a `return` statement at the end of their time at the center. Here's mine,
having recently wrapped up a half-batch.

## Motivations

At the beginning of this year, I found myself ready to move on from my current
job. I had spent the past 3 years as a staff engineer with a relatively high
visibility role, but my work wasn't tied to one particular long-term, technically
challenging project. I found myself embodying somewhat of a [right hand or a
roving tech lead archetype](https://staffeng.com/guides/staff-archetypes/), rather
than a solver. I had supported teams in delivering impactful, large-scale, and
technically complex solutions, but felt that I was acting more as a facilitator,
consultant, cheerleader, and champion. Certainly, I felt the work I was doing
was impactful, but at the end of the day, I didn't really feel like a _developer_
anymore. I was also having a hard time finding time to be a developer; even when
the opportunities presented themselves in my day job to write some code, I found
myself shying away from the work and instead leaning into mentoring others or
organizing work. This was a confusing feeling; I felt I wanted to be writing
code, but couldn't make myself do it.

When I began my job search, I wasn't quite sure what to look for, and I was having
a hard time feeling _excited._ I felt the need to move on, but I wasn't sure
_to what._ That's when I remembered [Recurse Center](https://www.recurse.com/),
which a mentor of mine had mentioned it to me years ago. RC provides the space,
time, and structure to program at the "edge of your abilities," partially with
the promise of becoming a dramatically better programmer. At the time, it sounded
like a magical opportunity that I'd never have the ability to take advantage of.
This year, something felt different. It felt like I _had_ to go.

So, while in the midst of applying for new jobs, I also applied to RC. Things
moved pretty quickly; within 48 hours of hearing back from the application, I
had completed two interviews, been accepted, and made the decision to attend. This
gave me only 3 weeks to quit my job, find a place to live in Brooklyn temporarily, and
move up there; quite a whirlwind! (I should note that RC allows attendees to attend
any batch that works with their schedule, and also supports remote attendance; it
was my choice to fully immerse myself by spending the time in person).

At the start of the batch, I set some intentions for myself; my overarching
goal was to fall in love with programming again. I had some secondary goals, most
of which were somewhat vague: to feel like I "deeply understood" some of the
technologies I work with day-to-day, to dust off an old hardware project and build
some visualizations, to read a few books, and perhaps explore some newer programming
languages. It may have been a bit ambitious for only 6 weeks. :)

## Themes

When friends and family asked what I did during my time at RC, my first instinct
was to start listing projects, or list skills or tools I learned. After reflecting
on this instinct, though, I craved a bigger picture reflection. Organizing the
experience into themes seems to better capture the "vibes" better than [my daily
logs or project summaries](https://katestud.dev/logbook/).

### Why and When to Learn

I have long known myself to be a "just-in-time" learner; learning a
skill or concept in order to complete a task has historically served as a better
motivation for me than learning something for the sake of learning or because
I may need it _someday._ While this strategy has generally served me well in
my career, I've felt a bit ashamed or embarrassed by it. It feels as if I should
know more, or that my knowledge is some how "less than" if it weren't gleaned
just by geeking out on a particular topic.

Given that, when I came to RC, I really wanted to learn for the sake of learning
and wanted to somehow evolve my learning strategy from one that I perceived as
somewhat naive. But, after a few attempts to "learn to learn," I found I wasn't
experiencing much joy. I began by working with the [maelstrom workbench](https://github.com/jepsen-io/maelstrom)
to better understand distributed systems, and started a series of tutorials about
programming for the Raspberry Pi Pico. While completing a particular tutorial
or chapter gave me some sense of progress or accomplishment, I didn't feel I had
much to show for what I learned, and I would sometimes end the day asking myself
if my time was well spent that day.

I also questioned my motivations for learning a particular tool; if I didn't
have an immediate plan
to use it, it was hard to know how far I should take my learning. Am I just seeking
a high level familiarity? Am I seeking some sort of expertise that might not serve
me in the future? Having the ability to reflect on _why_ I felt the need to learn
for the sake of learning helped me better formulate my learning strategy.

I realized
that in my just-in-time learning pursuits in the past, I would quickly move on
to the next concept once I had completed the task, sometimes without completely
absorbing _what_ I had learned, or exactly why a particular implementation worked
better than another one. Armed with this insight, I gave myself permission to again
learn just-in-time, but with a tweak; forcing myself to spend dedicated time after
writing some code to go back over what I had written, better learn the concepts,
and solidify the knowledge. This allowed me to both feel productive and get things
working, and also feel more secure in my knowledge. I was able at the end of the day
to say I had built something that worked, and also to be able to describe _why_
it worked. The practice of taking notes throughout the day aided in this practice,
because I could revisit learning materials after my commits were pushed and
revisit.

### To AI or not to AI

Not surprisingly, I encountered many different opinions on the role that AI should
play in any software development workflow. I really enjoyed a discussion group
that a fellow RCer organized where we discussed the role of AI in art; our responsibility as engineers as
(potential) users of AI technology, (potential) builders of AI technology,
and as creators of content which may be used to train AI; how individual
developer productivity is measured; the ethics of AI development; fears around
skills and learning atrophying; and many more concerns.

I enjoyed observing how others chose to interact with AI -- or not. Some
fully leaned into Vibe Coding and were first to try out new models as soon as
they were released. Others actively refused to interact with AI in any form. Most
folks fell somewhere in the middle of the spectrum, with many being simultaneously wowed by
what AI tools could accomplish, scared of what the future held (for both themselves
as developers and for the world as a whole), and somewhat skeptical that the tools
are as far along as some claim them to be.

When I first came to RC I was a bit hesitant to use AI in my workflow. I was feeling
burnt out on conversations about AI from my previous role, and I somewhat firmly
held the belief that using AI would be counter to my learning goals. This belief
evolved during my time at RC; I actively avoided "Vibe Coding" but did incorporate
AI into my workflow in a few modes. I found that using ChatGPT as a research tool or
as an idea generator felt like the most authentic use case. ChatGPT's responses
could serve as an initial jumping off point by suggesting a concept or a library,
and from there I could consult documentation and tutorials or riff on the ideas.
I also found that using AI (either Cursor, ChatGPT, or Copilot) to help write
boilerplate configuration code was one of the most effective uses of generative
AI. I generally had more success with boilerplate code than any attempts to ask
for help with application logic, for example; as many others have noted, once
Cursor would start trying to generate code, its attempts to fix bugs it introduced
would usually result in adding more and more cruft and logic rather than any
attempts to simplify.

In the end, while I continue to have concerns about AI's impact on society and
our environment, I have also found that it can be a helpful tool. What's most
important for me is to use it as I would any other tool; when it's the right
one for the job, and with intention. To use AI to augment or aid in a task
that I want to complete, rather than completing it for me.

### Embracing the mashup

A conversation with a fellow recurser, [Sophia Wood](https://www.fractalkitty.com/), early on in the batch still
sticks with weeks later. I was lamenting to her that I found it challenging to
do something "creative" and that I felt most creative work I had done in the past
was really just derivative. Not only did she help me feel more comfortable with
being derivative, she also suggested that one easy way to spur creativity is to take
two seemingly unrelated things and combine them to create something new.

One of the most fun days at RC for me was a mashup of one of my
projects with another Recurser's project. I had built a small app that visualizes
the rotation and position of a torus object (either based on pre-recorded or live data),
and Farid Rener had built a [lego sorter with a robot arm](https://github.com/huggingface/lerobot).
He suggested we could mash up the two projects -- using the robot arm to control
the torus on the screen. After a couple hours of pairing we were able to hook
the arm up to control not only the torus, but another web animation another recurser
had built. And we got it done just in time to [demo it at the Demo-palooza](https://youtu.be/j29avAvFT04)!

I'm still noodling on how to bring the idea of the mashup to other creative pursuits
but I love the idea of playing and creating something new by combining multiple
ideas together.

### Acting volitionally

RC famously has three guiding principles which make up the [self directives](https://www.recurse.com/self-directives).
These are working at the edge of your abilities, build your volitional muscles,
and learn generously. While all three of these directives shaped my time and
my experience at RC for the better, the workshops and conversations around building
my volitional muscle stood out. Exploring _why_ I wanted to work on a particular
project led to some interesting insights. For example, there was one project
that I kept getting stuck on, but I would find myself forcing or guilting myself
into working on it, mostly because I believed someone else expected me to be
making progress. Identifying that I was more extrinsically motivated than
intrinsically motivated on that project allowed me to let it go and focus on other
areas without guilt.

In one workshop, we were directed to write down a list of all the ideas for
projects we had, why we wanted to do them, and then make a decision about what
to do next. This exercise helped me identify that some of my ideas were thematically
similar and that some could be combined into a larger goal or project. This workshop
also helped me focus my efforts and decide to shelve some projects entirely. I found
that revisiting those questions throughout my batch to be a very helpful grounding
practice.

## Surprises

I wasn't quite sure what to expect when heading up to RC, aside from being inspired
and energized by the other attendees. I also expected to be a bit intimidated.

While all of those expectations came true, there were a few surprises along the way:

- **Diversity of Interests:** I wasn't quite sure what types of projects other
attendees would be interested in, but I was surprised by how wide a range of interests
there was, from game development, blockchain, creative coding, ML, hardware, to programming
languages. There were interesting overlaps across interests, and I found that I
learned something new from every conversation I had with another recurser.
- **Art!** I was surprised by how much of a focus there was on creative coding,
and how other recursers chose to create art using code. For some reason, I was
expecting the experience to feel more heavy or more serious, but so many people
were finding energy in creating art and visualizations. I found this focus really
reenergizing and it actually made me _want_ to write some javascript of my own
for creative pursuits.
- **My Own Contributions:** I was surprised at times at how much I had to offer
to other recursers whether it was encouragement and inspiration or my own expertise
and knowledge. I was able to help others with a range of topics from database
integration, ops, linguistics topics, authn and authz, and more. This was a bit
of a welcome surprise, as I expected to spend most of my time learning from others.
- **Schedule:** I was surprised by the hours that recursers chose to spend at the
hub! The core hours (when recursers are expected to be online) were 11 AM - 5 PM,
but I was still surprised to be one of the folks that showed up before the majority
of others. The hub was virtually empty if I arrived before 10 AM, and I found it
surprising that most collaboration and conversations seemed to happen in the
afternoon. This allowed me to have some focus time in the morning (and use the
soldering room!) when it was quiet, but it was still a bit of a surprise to me.

## The List

While enumerating what I worked on while at RC wasn't the motivation for this
return statement, I think it will serve as a source of inspiration in the future
when I look back on how I spent the time. So here's an incomplete list of things:

- I built a [static site generator](https://katestud.dev/rc/2025/03/14/a-book-of-logs.html)
that turns my daily notes into both daily logs and per-project logs.
- I gave two non-programming talks on [The Durham Accent](https://katestud.dev/the-durham-accent/)
and [screen printing with glass](https://katestud.dev/glassscreen/)
- I (with help from another recurser Kris) built a [visualization tool](https://aerial3d.vercel.app/) which visualizes
phone movements as well as pre-recorded hardware data, using React Three Fiber,
Accelerometer data, and PeerJS
- I built my own version of the classic pattern matching game [Set](https://setwell.vercel.app/) in React, which can also be run locally as an Electron desktop app
- I built a [physical Bop It! game](https://katestud.dev/rc/2025/03/25/building-beep-it.html), which required me to learn soldering skills, 3d printing and design, and more
- I paired with two other recursers Lucas and Freeman to build the first version of [the saurus fka thesaurle](https://github.com/katestud/thesaurle), a word-based game similar to semantle. This required learning about graph databases, [textual](https://github.com/Textualize/textual), and building up a dictionary of synonyms.
- I paired with others on many of their projects, including building an authentication system for a blog, many hardware projects, some leetcode challenges, rhyme analysis, morpheme detection, conways game of life, and more.
- I started working through the [maelstrom guide](https://github.com/jepsen-io/maelstrom)
- I played around with p5.js, and paired with a bunch of folks on a creative coding exercise inspired by the prompt "crunch"
- I played with so many fun hardware bits and bobs, including building a small simon says game and hacking around with a [pimoroni display pack](https://pimoroni.com/displaypack). I also organized a field trip to [Micro Center](https://www.microcenter.com/) with a few other recursers where we geeked out on 3d printing filament, audio tools, and more.
- I gave two tech talks on [bop it](https://katestud.dev/bop-it-preso/) and [the saurus](https://katestud.dev/the-saurus-preso/)

## The Result

My six weeks at RC were a whirlwind, and I'm still processing what I learned and
what I want to bring forward from my time there. I am happy to say that RC definitely
did reignite my excitement and passion for coding, and I did leave the experience
feeling much more like a grounded, competent, creative, energized developer.
Mission Accomplished!

While my time in Brooklyn is done for now, I'm grateful that alumni of the Recurse
Center Never Graduate. RC is an amazing resource and an amazing community that
I'm lucky to stay connected to. If RC sounds interesting to you, you [should apply](https://www.recurse.com/apply)!
I'd love to call you a fellow recurser.
