---
layout: post
title: "1.10: Tackling Larger Projects"
date: 2022-07-24 +0300
---

## Journaling

- Firstly, as you may have noticed, this post is a week late like the last one (NL0.9), and it is due to a significant
  **change in schedule**:
  - Even though the schedule for these posts is neither constant nor particularly reliable, as outlined in NL0.2, a
    repeating pattern for posts in the NL0.1-NL0.8 range was that **they were uploaded weekly** on Sunday or Monday.
  - This pattern was broken by NL0.9, that came out 2 weeks after NL0.8, though, as explained there, it was due to
    large productivity issues.
  - After careful consideration, I have decided to **switch the schedule to every two weeks**, e.g. bi-weekly.
  - My main reason behind this change is that I no longer have as much to show off every week, yet I want these posts
    to be large visible chunks of progress.
- Secondly, **the format version has been bumped from 0 to 1**:
  - As you may know, the versioning system (e.g. the _a.b:_ prefixes before post titles) is divided into two parts:
    the post number and the format version.
  - The version is now 1 with 3 changes:
    - References to prior posts (e.g. 0.8) are now explicitly prefixed with _NL_.
    - Bold formatting will now be used to better emphasize the key points of the text.
    - To break up large topics, nested headings will now be used, as well as some improvements to the _3D Graphics_
      section that you will later notice.
    - Proper punctuation (for instance, dots after sentences) will now be enforced.
  - The format version and the post number are not connected in any way! The fact that the format version in this post
    is the first digit of the post number doesn't mean anything, as I can and will bump the format version any time I
    want.
- Thirdly, a quick reminder that I'm going on vacation soon, so the next newsletter post (NL1.11) is expected to come
 out in mid-late August.
- Lastly, the _Competitive Programming_ and _Mathematics_ sections have been omitted from this post specifically, as
  there isn't much to show off even though I've been silently working on them as well.

## Website

- [The multitasking article]({% link _articles/creating-a-multitasked-workflow.markdown %}) has been released:
  - Its topic is setting up an efficient workflow that actively employs multitasking using a productivity app like
    [Trello](https://trello.com).
  - Alongside that, it covers the topics of multitasking itself, cost of productivity and choosing appropriate software
    for your needs.
  - I also feature my own workflow and the organizational approach I tend to use, which I omitted in the explanation in
    NL0.9.
  - I worked on it for quite a while, and I'm proud of what came out of that work.
- A draft of the [spaced repetition article]({% link _articles/rethinking-spaced-repetition.markdown %}) has been
  released:
  - It is an early draft, not the final article, so it is subject to be changed, rewritten or entirely cancelled. I've
    only published it to gather early feedback.
  - It covers the concept of a spaced repetition system and debunks some myths surrounding them.
  - The final version of the article is expected to be released within the next week or, in the worst case, after the
    vacation in mid-late August.

## German

- I've started reading literature in German to improve my active vocabulary:
  - My motivation behind this and some further background is noted in the
    [spaced repetition article]({% link _articles/rethinking-spaced-repetition.markdown %}).
  - Firstly, I tried a few books for my level (A2), but they were way too simple, so I turned to the same series of
    books I used for learning English.
  - And, surprisingly, after a rough start I started understanding about 70% of the entire text, which is motivating,
    as the text features (according to my analysis of the English version) B1-B2 vocabulary.
- On the regular side of things, I've worked through Unit 11 with its three micro-topics:
  - Entertainment & technology.
  - Radio and TV broadcasts.
  - Addiction to technology.
- The vocabulary was simple, but the Unit introduced two new grammar topics:
  - Mixed adjective declension (as mentioned in NL0.9, I learnt all types of adjective declension at once, but this
    book goes through them one by one).
  - Relative clauses (specifically, nominative and accusative relative clauses).

## 3D Graphics

### Project I. Doghouse

![The first render](https://github.com/kanpov/3DProjects/raw/main/16_Doghouse/Render.png)

---

![The second render](https://github.com/kanpov/3DProjects/raw/main/16_Doghouse/RedoneRender.png)

- This was a small practice project from the tutorial series, so I didn't learn much.
- New techniques learned:
  - The Curve Draw tool that allows you to free-hand draw a path and it efficiently and accurately builds out its
    segments.

### Project II. Beach Terrarium

![The first render](https://github.com/kanpov/3DProjects/raw/main/17_BeachTerrarium/Render.png)

---

![The second render](https://github.com/kanpov/3DProjects/raw/main/17_BeachTerrarium/RedoneRender.png)

- This was one of my prettiest creations so far: it features a glass bottle with a beach inside
- New techniques learned:
  - The Alpha setting on BSDF materials.
  - The built-in BSDF glass shader.
  - The Extra Objects add-on: Simple Stars.
  - Displaying an object as bounds in the viewport (as if it were an empty).
  - Spiral bevel resolution.
  - Using curves to directly represent objects.

### Project III. Low Poly Village

- Firstly, some background:
  - The beach terrarium project was the last project from 3DGreenhorn's tutorial series.
  - After completing it, I decided to venture outside using tutorials and work on some original projects, the first one
    of which is the following low poly village (though, this one specifically was made from
    [reference](https://github.com/kanpov/3DProjects/raw/main/18_LowPolyVillage/Reference.png)):

![The final render](https://github.com/kanpov/3DProjects/raw/main/18_LowPolyVillage/Render.png)

- This project gave me a chance to practice my low-poly skills (this style is low-poly + edge bevel) on a project that
  is significantly larger than what I usually make.
- It has several key parts:
  - The stone town hall in the middle with an entrance, windows, bricks and a flag on top.
  - The smaller minimalistic houses around the town hall with brick roofs, wood wall panels and simple-shaped windows.
  - The large clusters consisting of a long house and a small house that also feature a prettier entrance.
  - Several decorative elements:
    - Boxes
    - Barrels
    - Grass
    - Rocks
    - Trees
    - Lamps that actually glow due to having an emission BSDF material
- This was a pretty beefy project that took about 3 days of 4-5 hours of work each (approximately 15 hours in total),
  the modeling was quite enjoyable but the shading and lighting didn't turn out too well compared to the
  [reference](https://github.com/kanpov/3DProjects/raw/main/18_LowPolyVillage/Reference.png).

### Project IV. Large Castle Environment

- This is a hugely ambitious project I've started working on at the middle of the second week.
- The concept is to have a castle surrounded in a thick wall, outside which is a large town with Fachwerk (half-timbered)
  houses shielded by another, less thick wall.
- As is expected with such a large project, I haven't finished working on it and expect to be done by the end of the
  next week, so the project is likely going to be shown off in its entirety in NL1.11.
- Firstly, I'd like to introduce the several sources I used as reference to aid me in the tricky architectural parts of
  designing such an environment (see
  [this file](https://github.com/kanpov/3DProjects/blob/main/19_LargeCastle/Credits.txt) as well):
  - [Olbert's Low Poly Castle](https://www.unrealengine.com/marketplace/en-US/product/olbert-s-low-poly-castle) asset
    on the Unreal Engine Marketplace partially for the center of the castle:
  ![The top view of the referenced castle](https://github.com/kanpov/3DProjects/raw/main/19_LargeCastle/Reference_TopView.png)
  ![The side view of the referenced castle](https://github.com/kanpov/3DProjects/raw/main/19_LargeCastle/Reference_SideView.png)
  - [Low Poly Medieval Buildings Pack](https://sketchfab.com/3d-models/low-poly-medieval-buildings-pack-part-1-33ef8ae21a3c4ac59b51995f1d40b3f6)
    on SketchFab for the concept of an outer area for the castle:
  ![A screenshot from the SketchFab 3D explorer](https://github.com/kanpov/3DProjects/raw/main/19_LargeCastle/Reference_FullEnvironment.jpg)
  - [Olbert's Low Poly Medieval Town](https://www.unrealengine.com/marketplace/en-US/product/olbert-s-low-poly-medieval-town)
    asset on the Unreal Engine Marketplace partially for the architecture of the outer area
    (more specifically Fachwerk houses):
  ![The broken down modular assets from the pack](https://github.com/kanpov/3DProjects/raw/main/19_LargeCastle/Reference_HouseModules.png)
  ![The full top view of the medieval town](https://github.com/kanpov/3DProjects/raw/main/19_LargeCastle/Reference_MedievalTown.png)
- As for the progress I'm currently in the modeling stage and have completed several areas and key parts that I can
  already show off:
  - The central part of the castle with the central block and the towers connected to it:
  ![A screenshot of the central part of the castle]({% link cdn/20220724/CastleCenterScreenshot.png %})
  - The castle's inner walls surrounding its central part:
  ![A screenshot of the full castle center]({% link cdn/20220724/CastleCenterFullScreenshot.png %})
  - The castle's outer walls that will be housing the outer town area:
  ![A screenshot of the castle with all of its walls]({% link cdn/20220724/CastleAllWallsScreenshot.png %})
  - A modular half-timbered house-building model collection to assist me in making each house unique:
  ![A screenshot of the model collection]({% link cdn/20220724/CastleModularToolkitScreenshot.png %})
  - A demonstration of a half-timbered house to show off the model collection:
  ![A screenshot of a Fachwerk house example]({% link cdn/20220724/CastleHouseExample.png %})
