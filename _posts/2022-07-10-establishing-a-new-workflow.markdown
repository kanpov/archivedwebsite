---
layout: single
title: "0.9: Establishing a New Workflow"
date: 2022-07-10 +0300
excerpt: "This post is a week later than usual, mainly because these past two weeks have been very turbulent..."
---

### Preface

- This post is a week later than usual, mainly because these past two weeks have been very turbulent in terms of progress:
    - On the first week I didn't get much done, because I was away for a few days and had a sudden drop in productivity upon returning
    - So, I decided to postpone the post for a week in hopes of gathering more progress to show off
    - On the second week I worked on a new method of productivity to avoid overwhelming myself with tasks (which was the main reason for
      the drops in productivity I'd been having for a few weeks prior)
    - Afterwards, I started slowly regaining momentum and finally managed to accumulate enough to be able to show it off in the newsletter
- I'm also going on a vacation from late July to mid-August for two weeks, so there's going to be a 3-4 week break in the newsletter
- What was even more unexpected is that WSR got in contact with me and offered a free 3-5 day vacation within my country's borders
    - I've got no clue what that's going to be or whether I'll be able to go

### Website

- The former _English_ section has been merged with general website maintenance, because lately we've only been working on articles for the
  website
    - I'm also considering discontinuing the lessons after the vacation, since there's not much left for me to learn now
- Firstly, the website's theme has been updated to the latest version (Minima 3), and with that comes the ability to customize the "skin"
  (color scheme) of the website
    - So, the website now has a native dark theme and is much prettier to look at
    - For those who use the Dark Reader extension, I'd recommend whitelisting the website to get it to look correctly
- Secondly, I've replaced the old subscription method via [Mailchimp](https://mailchi.mp) with Jekyll's native RSS feed generator
    - This has various benefits:
        - Complete privacy for the readers (I no longer have access to any sort of view analytics for posts)
        - An automated publishing process (almost instantaneous delivery of emails)
        - Complete mirroring of the website's styling and content (no differences between the email & website version)
        - An archive of _all_ posts available within the feed, even older than 0.8
    - To migrate, follow the instructions at the top of the [newsletter page](https://kanpov.github.io/newsletter)
- Thirdly, the language learning article has been finished and largely renovated
    - It is the first addition to the articles section of the website and is available at [this location](https://kanpov.github.io/articles/the-happy-medium-of-language-learning.html)
    - Feel free to email me and give me some feedback on the contents
- Lastly, I've started working on a new article about productivity, which should be available next week

### German

- I didn't have German lessons in the first week, so this only covers a single week
- So, I began Unit 10 and worked through all of its micro-topics:
    - The Middle Ages
    - Fairy tales
    - Theatre acting
- The topics introduced some new vocabulary, but significantly less than the previous Units
- In terms of grammar, we revised the Präteritum (once again) and began a new topic of adjective endings
    - Essentially, there are three types of adjective endings:
        - Weak (_e_/_en_)
        - Mixed (_e_/_en_ and those derived from nominative definite articles (_ein gut**es** Buch_))
        - Strong (adjective has the function of a definite article)
    - The main hurdle here isn't even learning the endings (which are mostly self-explanatory), but learning
      to recognize the context and use them correctly

### 3D Graphics

- Firstly, I've made all of my 3D projects public over [here](https://github.com/kanpov/3DProjects) at GitHub
    - The repository contains number-prefixed folders, each representing one of my projects (it dates back to late May)
    - The folders contain the `.blend` file, which you can download and play around with and a rendered `.png`
    - I redo some of the projects, so the structure for those projects is (_X_ is the project's name):
        - _X.blend_
        - _RedoneX.blend_
        - _Render.png_
        - _RedoneRender.png_
    - The redone and original renders typically don't differ much
    - The [Git](https://git-scm.com/) commits most accurately represent my progress, so you can receive relatively
      frequent updates by checking the repository
- Project I: **Toast Shop**
    - New techniques learned:
        - Depth of Field camera effect (the farther an object is from the focus point, the more blurred it
         appears on the render)
        - Modeling stylized shapes only by manipulating vertices (useful for shapes like toasts)
        - Snapping object transformations to the nearest face (typically most useful with _Align Rotation to Target_
         and _Project Individual Elements_ options enabled)
        - Subdividing geometry with the _Fractal_ option (a multiplier that distorts the resulting vertices)
    - Renders (now are links to the GitHub repository instead of hosting the images here because it's less work):
![The first render](https://github.com/kanpov/3DProjects/raw/main/11_ToastShop/Render.png)
![The second render](https://github.com/kanpov/3DProjects/raw/main/11_ToastShop/RedoneRender.png)
- The next project was the birdhouse, but I couldn't finish it because the tutorial was severely incomplete
    - Though, I learnt a lot simply from modeling it
- Project II: **Mushroom House**
    - New techniques learned:
        - Rudimentary animal modeling (I'm planning on learning sculpting sometime as well)
        - Subdivide + Proportional Editing combination to deform shapes into rocks etc.
    - Generally, this was more of a practice project, so it wasn't necessarily hard to make
    - Renders:
![The first render](https://github.com/kanpov/3DProjects/raw/main/13_MushroomHouse/Render.png)
![The second render](https://github.com/kanpov/3DProjects/raw/main/13_MushroomHouse/RedoneRender.png)
- Project III: **Castle**
    - New techniques learned:
        - Using _Object Offset_ in the _Array_ modifier to loop an object using an _Empty_'s transformations
        - The _Weld_ modifier that merges the object's vertices at a certain distance (or anything lower than it)
        - Looping form-creating objects (like bricks) around a curve to create an arc (or anything of that sort)
        - The _Array_+_Curve_+_Weld_ modifier combination to create a continuous loop around a curve
        - More advanced emission materials
        - The _Boolean_ modifier to perform arithmetic operations on object geometry
        - The Boolean Tool addon that makes adding Boolean modifiers easier
    - I learned the most about using curves in practice, and it's definitely one of the most commonly-needed techniques
      I've learned so far
    - Renders:
![The first render](https://github.com/kanpov/3DProjects/raw/main/14_Castle/Render.png)
![The second render](https://github.com/kanpov/3DProjects/raw/main/14_Castle/RedoneRender.png)
- Project IV: **Treehouse** (my proudest creation so far)
    - New Techniques learned:
        - The _Normal_ transform orientation (uses directions of geometry to apply movement/rotation/scale)
        - The Extrude+Scale combination to create frames
        - Merging objects together (applies all modifiers of other objects and merges their geometry with the main
         object)
        - Extruding individual faces (all these types of extrusions honestly deserve a good explanation on their own)
        - Using Lattices (and, subsequently, the _Lattice_ modifier) to deform an object's geometry based on the shape
          of a grid
        - Using individual origins as the transformation pivot point (useful when bulk-transforming multiple objects or
          pieces of geometry and wanting them all to be transformed individually)
        - Snapping the active object to the 3D cursor (I have no clue why I hadn't known about this before)
        - Custom lighting colors
    - Renders (this is definitely going into my portfolio):
![The first render](https://github.com/kanpov/3DProjects/raw/main/15_Treehouse/Render.png)
![The second render](https://github.com/kanpov/3DProjects/raw/main/15_Treehouse/RedoneRender.png)
- Overall, these past few weeks were quite productive, but I focused less on other fields, so there won't be as
  much to show off

### Competitive Programming

- I finished the [C++ course](https://stepik.org/course/80538):
    - Completed the 4th module:
        - `std::vector<T>`s
        - `std::string`s
        - The final test
    - Completed the 5th module:
        - Quick console I/O (C `stdio.h` and accelerating `std::cin` and `std::cout`)
        - Number systems (and the conversion between them)
        - Storing numbers in a computer
        - Bitwise operations
        - The final test
- I also started a [competitive programming course](https://stepik.org/course/53634):
    - It is practice-oriented and describes the techniques used to solve common problems
    - I've started going through section about enumeration and have gone through these exercises:
        - Enumerating all possible `std::string`s out of the given characters with the given length
        - Recursive enumeration of all number sequences the length of `n` with numbers from 1 to `m`
        - Generating unique sequences (where a number appears only one time) with numbers from 1 to `n`
        - Generating correct bracketed sequences (that follow correct bracket syntax) of a given length
        - Generating all possible sums resulting in the given number
- In terms of VOS variants, I completed two (each one takes a few days):
    - The municipal 2021 tour ([tasks](https://olympiads.ru/moscow/2021-22/vsosh/okrug_archive/moscow-7-8-statement.pdf) and [answers](https://olympiads.ru/moscow/2021-22/vsosh/okrug_archive/moscow-7-8-tutorial.pdf))
    - The school 2020 tour ([tasks](https://vos.olimpiada.ru/upload/files/Arhive_tasks/2020-21/school/iikt/tasks-iikt-7-8-sch-msk-20-21.pdf) and [answers](https://vos.olimpiada.ru/upload/files/Arhive_tasks/2020-21/school/iikt/ans-iikt-7-8-sch-msk-20-21.pdf))

### Mathematics

- There isn't much to show off, so I'm just going to make a list of the new topics
- Geometry topics:
    - Polyhedrons
    - Unwrapping polyhedrons
    - Correct polyhedrons
    - Half-correct polyhedrons
- Algebra topics:
    - Factorizing polynomials (breaking them down into a product of polynomials)
    - Factorizing by extracting the common divisor
    - Factorizing by grouping the monomials together, extracting their common divisor and extracting the common divisor
      of the entire resulting expression
    - Factorizing by using shorter multiplication formulas in reverse (e.g. _(a-b)(a+b)=a^2-b^2_)
