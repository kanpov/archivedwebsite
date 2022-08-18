---
title: "(DRAFT) Journaling to Cultivate Work Ethic"
date: 2022-08-16 +0300
excerpt: "Excerpt not available yet"
---

## Introduction

This article aims to tackle the broad subject of journaling, the concept of journaling your work, the benefits of doing
so and the ways you could set up such a workflow. I also try to share some of my experience with journaling in general
and explain how it led to my current approach to journaling on this website.

As a disclaimer, this article only presents a specific and isolated way to approach journaling and writing that very
well may not be applicable in the context of your goals, writing style and personal preferences. I can only share what
has worked for me and hope that it will be useful to others trying to rethink their journaling mindset.

## My Experience with Journaling

My first attempts at journaling lasted only a few days each, as I failed to recognize the point of journaling, hence
failing to successfully integrate it into my daily routine.

The first time I managed to actually start journaling was at the beginning of September 2021. Back at that time, I was
recommended an excellent note-taking software called [Obsidian](https://obsidian.md) and quickly started integrating it
into my life as a storage for study notes, project documentation among other things. As I dove deeper into the
note-taking rabbit-hole, I encountered a practice called "daily notes", which essentially means writing up a note
(journal entry) every day.

I started making short, concise daily notes every evening after spending all of my prior free time working on my mod
projects. In the notes, I outlined in 2-4 paragraphs my key achievements for the day, which wasn't much, considering I
only had 2-3 hours of free time at best every work day. It was incredibly fulfilling to look back on even the smallest
accomplishments, plan forward and act on those plans, slowly getting closer to the project's completion. As short as
those notes were, they sparked my interest in writing in English and the size of the posts gradually grew alongside
noticeable productivity and motivation gains ([September 9th](/cdn/20220816/DailyNote20210909.png) and
[October 22nd](/cdn/20220816/DailyNote20211022.png)).

It was going great, until I encountered my biggest roadblock to continuing the journal: the ever-growing time burden.
For the first month or two, I had plenty of time at my disposal to crank out even the largest daily notes, but it all
started to change as I sunk deeper into a year-long game development competition and was forced to dedicate almost all
of my free time to preparing for the next round. The frequency of my posts declined, so I switched to making weekly
notes, but constantly shifted the schedule back and forth as my time budget and motivation grew and declined.

In late November, I was getting tired of this never-ending process and found about an incredibly simple command-line
program called [jrnl.sh](https://jrnl.sh) that granted me more freedom and dynamism in my journaling schedule. The way
it works is simple: type `jrnl {sentence}` into the command-line (where _{sentence}_ is a new fact or achievement), and
it will log the sentence into a plain-text journal file alongside the exact date and time. The program provides various
extra features, like powerful filtering and search capabilities, starred sentences and tags, so it suited my needs best
at the time.

My schedule loosened in January and February 2022, but in March I was forced to dedicate almost all of my time to
preparing for the final round of the competition, so I quit journaling for a few months and decided to rethink my
approach.

## Work-Oriented Journaling

At that point in May I was thinking about how I could start journaling again, as I finally had enough time to do so,
and I came to a few conclusions based on my experience:

1. My journaling methods were not sustainable in the long-term (half a year and longer), as my time budget increases and
   decreases rapidly. This was the main reason why I switched journaling methods every few months.
2. Journaling developed my planning skills, as I had to look back, write my progress and plan forward, not letting me 
   lose track of my goals and projects (which often was the main reason I abandoned many of them).
3. Journaling increased my motivation when working on larger, long-term projects. The more I managed to do, the more I
   could write down and look at afterwards.
4. Keeping up a constant schedule for journaling is stressful and near impossible, because it is impossible to maintain
   a constant standard of progress and productivity over a long period time (especially if you aren't working full-time).

Taking these into account, I developed a new approach that I call work-oriented journaling. The main difference in
comparison to what I did earlier was that it is solely focused on compounding, writing out and looking back at my work.

A work journal is meant to cultivate work ethic, increase productivity, develop motivation, encourage discipline and
responsibility in the context of heavily multitasked workloads, where getting lost under the burden of various
concurrent projects is only a matter of time.

Not even the best productivity tool can fight that reoccurring feeling of emptiness that tears you apart from inside.
_"Why am I doing this?"_, _"What have I accomplished?"_, _"What am I really working towards?"_ are the questions that a
work journal makes you constantly answer. Having a strong foundation, a sense of meaning is invaluable to completing
your projects and achieving your goals.

## Setting Up a Work Journal

To demonstrate how a work journal may look like, I'm going to provide the example of my own work journal that is hosted
on this website - [the newsletter]({% link newsletter.markdown %}).

The workflow I use is powered by the [Jekyll](https://jekyllrb.com) static site generator. Jekyll operates on different
types of text files and transforms them into special web files like HTML, CSS and JavaScript that are then deployed
onto this domain using [GitHub Pages](https://pages.github.com/). GitHub Pages is a free hosting provider that automates
the deployment process and improves the workflow with a version control system called [Git](https://git-scm.com/).

The main type of those text files is [Markdown](https://www.markdownguide.org/getting-started/), a robust and
easy-to-use markup language that allows you to write and style your text (bold, strikethrough, lists, headings and much
more) without using an unreadable proprietary format like Microsoft Word. This means that my writing is entirely
future-proof, since you don't even need special software to read and write Markdown because it is based on plain text,
and there are hundreds of Markdown editors to make editing quicker. To get a grasp of how Markdown looks like, see how
[this post](https://raw.githubusercontent.com/kanpov/kanpov.github.io/main/_articles/journaling-to-cultivate-work-ethic.markdown)
looks like as plain text.

So, all the posts, articles and other content on the website is written in Markdown. Posts and articles are stored in
their own directories, allowing Jekyll to easily distinguish them from one another and other pages. Every post and
article has special information attached to the top of it: the title, time of publishing and an excerpt. Using this
information, the posts and articles can be displayed on the homepage and their dedicated pages.

Your setup doesn't matter much to the quality of your journal, but if you want to publish your journal onto the web as
a sort of blog, this might work for you.

## Maintaining a Work Journal

Work journaling is fundamentally volatile. Your journal should only be based on your will to write and the progress you
manage to make, not on the schedule you want to establish. Setting goals and standards is generally beneficial, but I
believe it only hinders your journaling and writing in general, making you sacrifice quality to keep up with a schedule.

My personal rule is to release a new post as soon as I have enough work that I'm proud enough of to write about and
show off. Such an approach in combination with a passion for writing would establish a relationship between your volume
of progress and ability to write, adding another factor to boost your motivation.

A work journal can also be versioned to keep track of changes you make to your writing style and encourage those
changes to be made when needed. I suggest using an `f.n` versioning system, where `f` is the format version and `n`
is the number of the post (for example, in my latest post at the time I'm writing this is 1.10, where `f`=1 and `n`=10).
Since work journals are volatile, a versioning system can help you record your journal's evolution over time.

## Incorporating Organizational Tools

**Under construction**.

## Conclusion

**Under construction**.
