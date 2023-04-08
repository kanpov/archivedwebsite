---
title: "1.11: Wrapping Up the Summer"
date: 2022-08-21 +0300
excerpt: "Such a post frequency might not be ideal, but as you may have noticed by my track record, I tend to prioritize..."
---

## Preface

- This post spans a whole month, of which 2 weeks I spent on vacation and the rest working on my projects.
- Such a post frequency might not be ideal, but as you may have noticed by my track record, I tend to prioritize quality
  over consistency.
- It is currently the end of August, so I'm only a week or two away from starting the school year and no longer being
  able to work full-time (as I've been doing since June).
  - I have reasons to expect a heavy workload in terms of studies, so I expect to be able to allocate only around 12-16
    work hours each week (in comparison to about 45-50 hours I dedicate nowadays).
  - The frequency between posts will likely deteriorate even more alongside their volume.
- On another note, I'm planning to apply as a 3D artist to a year-long game development competition in late September.
  - My main aim with this is to improve my 3D skills with the training of an experienced artist (unlike me).
  - The success (or failure) of this application will determine the direction going forward:
    - If successful, I'll likely have to dedicate most, if not all, of my free time to prepare for the competition.
    - If unsuccessful, I'll continue trying to learn 3D art on my own with my limited time budget.
  - In the meantime, I've continued working on my projects and preparing for the beginning of my studies.
- I don't have much to share with my German progress just yet, hence why the section isn't present in this post.

## Website

- The website has received a major visual overhaul and several other improvements.
  - I was unsatisfied with the looks of the website when it was using Minima v3 (the old theme), so I decided to swap it
    out for another one - [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/).
  - Minimal Mistakes is a more modern option that offers better visuals out of the box and a lot of room for
    customization and personalization.
  - Changing themes in [Jekyll](https://jekyllrb.com) (the content management system empowering this website) is an
    incredibly frustrating process that looks somewhat like this:
    - Back up your old site's content (articles, posts and other Markdown pages).
    - Generate a new Jekyll website and manually switch the theme via the build configuration (`Gemfile`).
    - Copy all the old content into the new website.
    - Spend days reading the theme's documentation, 8-year-old blog posts and source code in order to get the styling
      you want.
    - Copy the Git repository files from the old website, push to GitHub and hope you build configuration won't break
      in production.
  - Nevertheless, I managed to get through it and the website looks much more fresh and presentable.
- The [spaced repetition article]({% link _articles/rethinking-spaced-repetition.md %}) has been released out of
  its draft stage.
  - Added bold formatting to the key points of the article.
  - Clarified that the article is about memorization, not learning vocabulary as a whole.
  - Separated the principles of spaced repetition into their own heading and made them clearer.
  - Aside from these changes, no major edits have been introduced.
- A draft of the [journaling article]({% link _articles/journaling-to-cultivate-work-ethic.md %}) has been released.
  - It provides more background on this newsletter approach, why I chose it and what I had used prior.
  - I've received some valuable feedback about its content, therefore it will undergo various changes before the final
    release.

## 3D Graphics

### Castle Housing

- First, I used the half-timbered house part collection presented last time to create 6 unique house designs:
![1](/cdn/20220822/CastleHouseDesign1.png)
![2](/cdn/20220822/CastleHouseDesign2.png)
![3](/cdn/20220822/CastleHouseDesign3.png)
![4](/cdn/20220822/CastleHouseDesign4.png)
![5](/cdn/20220822/CastleHouseDesign5.png)
![6](/cdn/20220822/CastleHouseDesign6.png)
- Afterwards, it was just a matter of placing them down inside the castle walls:
![Perspective 1](/cdn/20220822/CastleWithHouses1.png)
![Perspective 2](/cdn/20220822/CastleWithHouses2.png)

### Castle Marketplace

- Next, it was time to add marketplace tents to the main town area of the castle.
- For this, I used the [low poly medieval marketplace asset](https://www.cgtrader.com/3d-models/architectural/architectural-street/low-poly-medieval-marketplace)
  on CGTrader as reference.
- First, I recreated three tents from that asset to later deconstruct them into another model collection:
![Demo bread tent](/cdn/20220822/DemoBreadTent.png)
![Demo fish tent](/cdn/20220822/DemoFishTent.png)
![Demo meat tent](/cdn/20220822/DemoMeatTent.png)
- After that, I took apart the pieces of the tents and assembled them into this collection:
![Market model collection](/cdn/20220822/MarketModelCollection.png)
- Then, I created 9 tent variants (3 bread tents, 3 meat tents and 3 fish tents) using that collection:
![Market tent variants](/cdn/20220822/MarketTentVariants.png)
- Lastly, I put those tents together and got this result:
![The castle with these market tents](/cdn/20220822/CastleWithMarketTents.png)

## Competitive Programming

- Since NL1.10, I've also been focusing a ton on resuming my efforts of trying to learn competitive programming.
- I've decided to switch from C++ to Python as my main competitive programming language for a variety of reasons:
  - C++'s standard library lacked or obscured tons of fundamental features, such as extensive string manipulation,
    iterator utilities, collection tools like Python's `map`, `filter`, `any`, `all`, `zip`, `enumerate` and others.
  - C++ heavily compromises on speed of writing code for the sake of runtime performance, but I believe being able to
    quickly prototype algorithms is invaluable in a competitive context.
  - There are much more learning resources for Python provided by the competitions that I'm trying to participate in.
- So, I've taken two multi-month courses on [Stepik](https://stepik.org) for learning Python that cover various basic
  and intermediate topics.
- The first course goes through the basics of programming, so I flew through it pretty easily:
  - Console I/O and simple arithmetic
  - Branching and basic data types
  - `for` and `while` loops
  - String manipulation, indexing and substring syntax
  - Working with lists (arrays)
  - Creating functions
- The second course goes through more intermediate and practical topics:
  - `bool` and `NoneType`
  - Nested lists
  - Matrices and basic matrix math
  - Tuples (immutable lists)
  - Sets (unordered hashed unique collections that support various mathematical operations)
  - Dictionaries
  - Extra modules: `random`, `string`, `decimal`, `fraction`, `complex`, `turtle`
  - Advanced functions and functional programming concepts (high-order functions, anonymous functions etc.)
  - Tools for working with collections: `map`, `functools.reduce`, `filter`, `any`, `all`, `zip`, `enumerate` etc.
  - Basic file I/O
- So, I've put the better part of two weeks into going through these courses, and I'm going to focus on competitive
  programming on the side for the next few weeks or so.
