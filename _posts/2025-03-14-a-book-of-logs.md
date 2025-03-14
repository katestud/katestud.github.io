---
layout: post
title:  "a book of logs"
date:   2025-03-14 15:34:03 -0400
categories: "rc"
---

I've spent the past four weeks (I've got two weeks left!) at Recurse Center (RC) in
Brooklyn, with the intent of programming at the edge of my abilities, to borrow
their words. For the past few years, my role as a staff engineer has frequently
taken me further from the programming and coding work that got me into the industry
in the first place, and I miss it! When I was a junior dev and recent bootcamp
grad, I frequently spent time in the evenings coding up personal projects or
learning new concepts. More recently, I've found that I gravitate towards hobbies
that take me far away from the computer, such as [powder coating](http://sprightconcepts.etsy.com/),
writing, linocut, cooking, or anything else I can do with my hands. But still, I
miss writing code just for myself.

During my first week at RC, I was reflecting on why I've shifted away from
coding as a hobby. Burnout surely played a role, but I also identified that
the cognitive demand required to "pick back up" where I left off was really
weighing on me. It's not easy to spend, say, an hour "now and then" working on a
side project. I have to spend that time ramping up on what I was building and why,
remember why I last got frustrated, remember how to run the code, etc. And, while
a list of GitHub repositories provides some way for me to list my projects, it's
not quite sufficient for my needs -- it'd require that I keep all my READMEs up
to date and put a lot more thought and effort into organizing knowledge than
I really want to. I'd prefer if my knowledge were already organized for me.

I also had planned to be more intentional and diligent about note taking during
my time at RC. I find it's easiest for me to take daily notes by creating a new
file each day. This approach makes it really easy for me to answer the question
about what I completed or discovered on any given day, but it wouldn't serve the
need of helping me ramp back up on a project that had been neglected for a while.
I was inspired by how [Reed organized his projects on his website](https://reeds.website/topic-project-index)
and decided I wanted to build my own little spin on it. Maybe there was a way
that I could take notes the way that it was easy for me, but transform them
into something that would also be easy to _consume_ at a later point in time.

Thus, Logbook was born! This was one of my earliest projects at RC, although
admittedly a simple one.

## Requirements

- Allow me to take quick and easy daily notes in markdown. These should be able
to be presented as a daily log.
- Allow me to tag the notes with a particular project or topic. Daily notes should
be able to include notes across many projects, the same content should be able to
be tagged to one or more projects, and not all of the content must be tagged.
- Content tagged with a particular project should be presented in chronological
order, with date headers, for easy project-based consumption at a later time.
- I shouldn't need to do anything special to deploy this. Pushing to my repository
should be enough.

## The Solution

I'm already familiar with GitHub Pages and Actions. Since GitHub Pages can host
static content, I figured that if I could write a simple script to convert
the markdown into static content then I could easily deploy it with Actions. So,
the biggest problem to solve would then be figuring out the best way to parse
the markdown.

Luckily, I found the [kramdown](https://kramdown.gettalong.org/index.html) library,
which is a Ruby library for parsing markdown and converting to HTML. It's also
pretty fast! After playing around with it, I found it would work well for my
use case, partly because it makes it very easy to extend their built-in converters
and also because of its [Attribute List Definitions](https://kramdown.gettalong.org/syntax.html#attribute-list-definitions).

Let's look at the attribute list definitions first. These definitions allow
for defining arbitrary key-value pairs in the markdown itself, which are parsed
by default into HTML attributes. In my case, I chose to use the key `project`
to denote when a particular block of content is associated with a project. The syntax
looks like this:

```
My really awesome notes about the coolest project!
{: project="cool-project"}
```

kramdown will parse that content and add an attribute to the resulting converted
HTML:
```
<p project="cool-project">My really awesome notes about the coolest project!</p>
```

While that's a little weird because project isn't a "real" HTML attribute, it
works well for my use case because the content is tagged for each HTML element,
including block elements such as `<ul>` elements. This makes it easy to slurp
up these elements and plop 'em wherever I need them in my files.

Once I decided on the syntax I wanted to use, I had to figure out how to create
a converter which would intercept these elements as they were getting created.

I decided to do this by creating a new converted class that inherits from the
standard HTML converter and collects all the elements in a Hash, keyed by the
project name. It looks something like this:

```
module Kramdown
  module Converter
    class SpecializedHtml < Html

      def initialize(root, options)
        @collector = options[:collector]
        @collect_key = options[:collect_key].to_s

        super
      end

      def format_as_block_html(name, attr, body, indent)
        converted = super(name, attr, body, indent)
        collect(attr, converted)
        converted
      end

      def collect(attr, html)
        return unless @collector

        attr.each do |name, list|
          next unless name == @collect_key
          list.split(" ").each do |v|
            @collector[v] << html
          end
        end
      end
    end
  end
end
```

My `SiteGenerator` class can then "simply":

- Create a project log collector to track all project logs across all daily files
- Iterate through all markdown files in the daily log directory
- Convert all daily log files to HTML using the specialized converter
- Iterate through all the collected project log HTML and build the static pages for
the projects
- Make sure the files go in the right directory, etc. etc.

A `build` script in the directory runs all this code and outputs it to a `build`
directory that GitHub pages can use to source the content.

The end result includes:

A listing of project logs:

![a list of project logs](/assets/project-log-listing.png)

Nicely formatted individual project pages, with content relevant only to that project:

![some text describing a project](/assets/project-log.png)

And fully intact daily logs:

![some text from a daily log](/assets/daily-log.png)

## Some Takeaways

This isn't a perfect solution. For one, the implementation is a lil' funky.
Because my converter collects individual HTML block elements, that means if
I have multiple paragraphs about the same project, I must tag each one with the
project. I'm okay with this tradeoff for now because I wanted the ability to be
very selective about what notes are relevant to a project or not. I also tend
to take notes in bulleted lists, so I only need to tag the list once.

The build script and my HTML templates are also somewhat brittle. This seems to
work fine for now, but it seems that these static site generator projects always
balloon into something much more complicated over time. We'll see if I can keep
it simple.

A note about design. I wasn't sure what template I wanted to use for this site.
[Sophia](https://www.fractalkitty.com/) encouraged me to play with different
designs and design it just for me. It _is_ just for me, after all. So, I went
kinda funky with a funky font and a colorful gradient background. And I like it.
Feels cute, might change it later.

Only time will tell if this will help address the original project it was designed
to solve. Will it encourage me to pick up side projects more frequently? That
honestly feels a bit like a tall order. But I did already find some utility in
the project notes when pairing with someone on a shared project. We couldn't
decide or remember where to pick back up. A quick look at logbook reminded us
where we had left off and got us back on track.

Overall, feeling optimistic about how this tool will support me in the future.
As long as I remain intentional about note taking. 😉
