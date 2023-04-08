---
title: "0.3: A Daunting Future in 3D"
date: 2022-05-22 +0300
excerpt: "Implemented the repair system, made some minor improvements and added some final polish..."
---

### German

- Lesson highlights:
  - Revised the two-way prepositions topic a little
  - Introduced a lot of new vocabulary regarding indoors objects (walls, chairs, sofas etc.)
  - Did a small pronunciation exercise
  - Started a new Unit (8), which expands on the city topic, introducing vocabulary, such as pedestrians, ~~police men~~
    police officers (hehe)
- Added new vocabulary to Anki and jammed through it
  - Was around 50-70 words, as I recall

### English

- I was sent my homework about another TED talk pretty late, which... caused some issues
  - I opened up a Google Document late in the evening as soon as I had finished my studies and started rushing through
    the exercises
  - As a result, I ended up with a short document full of brief notes at, like 10 PM, and a stressed out nerve system
- Hopefully, that issue should be fixed now, and I'll be able to exhaustive notes for the next TED talk in a reasonable
  timespan
- On the lesson itself, I managed to go through about 80% of the talk, but there were still some parts I just hadn't
  had the time to even review

### ResourceRun

- Preface:
  - This will be a short update, as I took a break this week after the rather chaotic leaps in progress
    [last time]({% post_url 2022-05-15-implementing-resourcerun-gameplay-loop %})
  - On Saturday and Sunday, I focused a little on a bit of research (read on to find out)
  - Another factor to the productivity was the enormous task of XML commenting the entire codebase, which was quite
    tedious and frustrating to do, so I ~~wasted~~ spent 2-3 days just on that
  - Nevertheless, I managed to check a reasonable amount of systems off my milestones' lists and start v0.3
  - I don't think I'll be moving forward with the game past v0.3/beginning of v0.4 in the near future, as I have
    different priorities now
  - Taking that into account, the MVP (minimal viable product) is almost certainly going to be complete by next Sunday
- Implemented the repair system
  - This required a few more extensions to the UI sprites that I had previously had
  - I designed the entire UI, which was simple enough, and the toggle icon
    - The main shiny thing I added for this UI panel was a progress bar that delayed the completion of the repair bar
      for a certain amount of time, while being pretty satisfying to look at
  - I added a bunch more relatively complicated statistics to the `ToolItem`:
    - The repair efficiency, which represents the amount of durability that will be repaired at one go
    - The repair cost, which represents the amount of the material that this tool is made up of that is required to
      repair this tool
  - There are a bunch of internal calculations and details that I won't touch on in this post (you can inspect the
    game's [source code](https://github.com/kanpov/ResourceRun) if you'd like to learn more) that are required to make
    these stats work
  - Linked up all the UI elements to the script
  - Tediously implemented the internal conditions and data synchronization between the script and the UI panel
  - The panel can be opened and closed with the `LeftShift+R` key or by pressing the dedicated icon
  - Implemented the satisfying repair progress bar and the result of the repair
- Made some minor improvements and added some final polish for v0.2
  - Added an alternative to open the tooltip screen with an icon
  - Added a button to compress the inventory manually
  - Added a shortcut for inventory compression
  - Appended all shortcut buttons with a `LeftShift` press (e.g. `U` => `LeftShift+U`)
  - Made the player able to organize their inventory, clicking on two items in the HUD makes them swap
  - Implemented hints about the selection preferences above inventory slots
  - Added a cancel button when trying to swap, that clears all selections
  - Fixed the compression operation to back-shift by the maximum amount possible instead of one every time
  - Separated the deduplication operation from the compression operation (see the internal descriptions from
    [last time]({% post_url 2022-05-15-implementing-resourcerun-gameplay-loop %}))
  - Made the player only able to move with WASD, not arrow keys
  - Added slot switching with arrow keys
  - Removed slot switching by clicking on the outer frame of a slot
- Cleaned up the code
  - Started using namespaces everywhere possible
  - Refactored in some places
  - Added XML comments to the entire codebase, which crippled my sanity
- Added switching between different seasons when the player falls
  - Exposed the `Season` as a regular, non-serialized property in the `WorldGenerator`
  - Started storing a list of all `Season`s
  - Implemented the invocation of the next season's generation or game over when falling
  - Added a simple animation with the player slowly disappearing over the course of a few seconds when falling
  - Started putting the player exactly into the center of the tile they're falling into
- Added summer into the game
  - Added summer grass based on the old sprites
  - Implemented loot multipliers in `ObjectGroup`s that allow to globally multiply the amounts of loot in a 
    `GatherableLootTable`
  - Added summer ores
  - Added summer trees
  - Added summer bushes

### A Glance into the Future

- Over the past month, I've come to the conclusion that the most logical way forward is to learn 3D game development
  - I've already learnt the most that there is about 2D game development, which was only amplified in the process of
    developing the ResourceRun project
- To be specific, I'm interested in 3D VR development (possibly AR as well)
- But, as soon as I dug deeper into the requirements, I realized, that this field is so much more difficult than
  what I'm currently used to with tons of skills required to do anything
- So, this is sure going to be hard, but I'm all up for the challenge!
- My initial stack is [Unity](https://unity.com), [JetBrains Rider](https://www.jetbrains.com/rider/) and
  [Blender](https://blender.org)
- Next week, I'm going to start learning 3D graphics in [Blender](https://blender.org)
