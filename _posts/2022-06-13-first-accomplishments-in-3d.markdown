---
layout: post
title: "0.6: First Accomplishments in 3D"
date: 2022-06-13 +0300
---

### English

- This week, we've been working on another [TED talk](https://www.ted.com/talks/chris_anderson_ted_s_secret_to_great_public_speaking/)
  called _TED's secret to great public speaking_
- To sum it up, TED speakers' main goal is to transfer the idea of their talk to the listeners _in any way possible_
- This rekindled my main concern about TED talks: they provide little practical value beyond spreading (often in highly
  manipulative ways) the idea
  - They strive to get the short-term attention of their listeners and advertise the main idea to them
  - But, besides a few rare gems (like the talk about multitasking I wrote about in 0.5), the talks provide little
    reason to care or act upon the idea after watching (or, in my case, analyzing) the talk
  - And, without any particular sense of direction or hint towards its implementation, any idea (in my opinion) is
    practically worthless and turns into a source of something I call _educational entertainment_
  - And that's perfectly fine for a platform that advertises itself purely for entertaining its viewers
  - However, TED advertises itself (not necessarily officially, but through the intrinsic motives shared in their talks'
    content) as a self-improvement and learning program
  - This has misled me when making my analyses and working on these talks
- All of this is not to disregard TED talks as a method of language learning, but as a platform designed for learning
  and personal growth
- I did some exercises that I'd received and expressed my position during the lesson

### German

- We first practiced some grammar and dialogue (again), then finally moved onto a new Unit
- This Unit has, once again, three micro-topics:
  - Sweden, its culture, territory and languages spoken there
  - A dog that apparently helped people out during snowstorms (I'm just as confused as you are)
  - Inventions over the course of history
- We've worked on and finished the first two micro-topics
- This Unit has finally introduced some new grammar (which I studied on my own three months ago)
  - First, German grammar was my main source of frustrations due to me discovering new grammatical concepts in the context
    of a foreign language
  - But now I've pretty much grown accustomed to it and enjoy learning it much more than other aspects of the language
    (especially vocabulary) as it's become much easier

### 3D graphics

- This week I've so far been the most proud of in terms of my progress in learning 3D art/graphics, as I've begun making
  projects completely on my own
- Firstly, I continued working on and finished the bedroom project, the progress on which I briefly showcased last time
  - As mentioned last time, I took apart into separate pieces for each room the demo reference image from the paid
    course on Gumroad by the author, whose tutorials I'd been using for learning the basics of modeling
  - The first new room was this bedroom
  - The primary difficulty that I had with it were the more complex shapes, like the lamps and the geometrically
    convoluted blanket on the bed
  - Nevertheless, I managed to overcome these issues and completed the modeling part successfully
  - The lighting is pretty bad in several areas, as I encountered various lighting-related artifacts on the scene and
    had to insert an excessive amount of lights to fix them
    - This was certainly unnecessary, and I just was and still am a complete moron in lighting
  - The materials and colors look slightly weird in some parts
    - That was because I hadn't managed to gain access to the exact color codes when I was adding the materials and tried
      to use a color picker to extract the colors from the reference image
    - This didn't work out so well due to reflections and the high contrast effect applied on top of the colors
    - After finishing the project, I learned from my mistakes and picked the colors manually for the next project,
      which turned out better in terms of colors
- Here's my result:
![The rendered image of the bedroom scene]({% link media/20220613/BedroomRender.png %})
- In contrast to the reference image pinned below my result looks visibly worse, but this was my first ever
  original project, so I guess this wasn't anything out of the ordinary:
![The original reference image of the bedroom scene]({% link media/20220613/BedroomReference.png %})
- As my second project for the week, I took the bathroom from the same series
  - There were much more complex (e.g. non-rectangular) shapes, like the mirror, sink and the objects on the table
  - This room took me longer to create due to these difficulties, but it turned out relatively successful
  - The only thing I couldn't make was the toilet, but I'll get back to it eventually
  - The lighting is still mediocre, but significantly better than the last room because I only used four lights:
    - The light on the top
    - The light covering the right side of the room
    - The light covering the left side of the room
    - The light in the back to better illuminate the background plane
  - The materials and colors for technical reasons don't match, but look pretty well
    - This time, I turned on high contrast and started picking the colors myself
    - With some saturation manipulation I tweaked everything a bit, and it turned out nicely
- Here's the resulting render:
![The rendered image of the bathroom scene]({% link media/20220613/BathroomRender.png %})
- The reference image is still better, but I think this was a significant step-up from the last project's quality:
![The reference image for the bathroom scene]({% link media/20220613/BathroomReference.png %})
- I also would like to draw special attention to the drawer, as it was one of the most detailed parts of the scene
  (don't mind the bug with the metallic effect, it only occurs in the isolated view of the drawer):
![The rendered image solely of the drawer, zoomed in]({% link media/20220613/BathroomDrawer.png %})

### Programming

- As mentioned last time, I didn't spend much of my time on programming this week
- Though, I finally finished the C++ course with these sections complete:
  - Functions and recursion
  - `std::string`s and doing horrible things with characters
  - `std::map`s (dictionaries) and `std::set`s (unique-element-only `std::vector`)
  - Standard library algorithms in the `algorithm` header (`std::sort`, `std::reverse` etc.)
- At the end of the week my motivation and productivity started falling as I wasn't doing any programming (and I still
  enjoy that much more than 3D art)
- So, I was looking for a side-project to work on meanwhile I'm learning 3D art
  - Jumping into 3D games with only a pretty shallow understanding of the art pipeline doesn't seem like a good idea
  - However, I can still pick up and finish the [ResourceRun](https://github.com/kanpov/ResourceRun) project from a few
    weeks ago
- I have no updates on this just yet, but expect some amount of progress on ResourceRun in next week's update

### Mathematics

- In terms of geometry, I didn't do that much, just went further along the fundamental curriculum
- But for algebra I managed to finish 2 blocks of topics:
  - Systems of linear equations with two unknown values ([this stuff]({% link media/20220613/SystemOfEquationsExample.png %}))
    - The definition of a system of equations
    - Solving systems of equations:
      - Graphically (create graphs of both equations and the intersection point's coordinates will be the solution)
      - By representing one unknown value through another (which makes an equation with only a single unknown value)
      - By adding or subtracting the equations in the system in a way that excludes one of the unknown values from the
        resulting equation
    - Formulating a system of equation for a text-based task and using it to solve that task
  - Powers of numbers (of course, we started it in 5th grade, but this block expands upon that knowledge)
    - Revision of previous knowledge
    - Properties of powers (e.g. _a^b * a^c = a^(b+c)_)
    - Power of zero
