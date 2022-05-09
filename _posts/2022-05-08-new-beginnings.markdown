---
layout: post
title: "New Beginnings"
date: 2022-05-08 +0300
---

## Journaling

- On May 12th this year I temporarily stopped journaling. This was for a variety of reasons:
    - The preparations for WorldSkills (more on that in an article coming soon) exhausted my time and energy
    - The technique I used was horribly inefficient, requiring me to spend about an hour every day writing up a long rant
    - It started seeming pointless to me, because I was unable to share my hours of work with anyone else
- Since then, more than 1.5 months have passed and the distraction has gone away, so I decided to come
  back to consistent journaling
- But, I decided to make some major changes:
  - Instead of trying to pump out a post every day, I decided to starting making posts every week on Sunday
  - The purpose of the posts had to shift to just be a method of capturing information, not a productivity app
  - For productivity, I returned to the [Trello](https://trello.com) app, allowing me to effectively
    summarize my boards into a post with more detail
- Then there was the choice of software to empower the journaling process:
  - I used to use [Obsidian](https://obsidian.md), but I recently dropped it for [Anki](https://apps.ankiweb.net) flashcards
  - There are software like [Revue](https://getrevue.co) that allow me to send out posts into people's emails, but they are inherently flawed:
    - Custom format instead of Markdown
    - No import from Markdown
    - No export to any sort of parsable format
    - No guarantee of longevity of posts
  - In the end, I settled on posting everything on this custom website powered by [Jekyll](https://jekyllrb.com), which
    gives me the maximum amount of features and flexibility
  - As a bonus, I'm also planning on making articles here
- So, after a few hours spent on setting the website up and the newsletter system, this is the first post!
- I am planning on porting over my old posts, but no promises yet!

## German

- Finished migrating my entire German collection of vocabulary from Obsidian to Anki flashcards
  - It all totaled in about 850 flashcards
  - That's not really a lot, considering I haven't even added all the words from the glossary, only the major highlights
  - I'm planning on reviewing the glossary for all past Units to see whether I missed any important vocabulary
- Relearned and revised all this past vocabulary, refreshing some older topics in mind
  - I started the review all the way back on Tuesday, yet only finished it on Saturday
  - I learned a lot about reviewing large decks in [Anki](https://apps.ankiweb.net)
- Ported all my theory for grammar as well, which was a tad bit more painful to accomplish
  - My main reference source for German grammar is [this excellent website](https://germanveryeasy.com)
  - I decided to completely rewrite my notes in the process of porting them, which significantly increased the time spent
  - Plus, I added a bunch of new theory on some other topics I wanted to study prematurely
  - Lastly, I re-studied all the older grammar just to make sure I haven't forgotten anything important
- Highlights from the lessons:
  - I had a test on the past 6 Units, combining all the vocabulary and grammar concepts from the past 3-ish months
  - Half of the test we did on the lesson, the rest I pushed myself through in the homework
  - The test wasn't hard, especially after my recent migration to flashcards I had zero problems with the vocabulary
  - Then I started a new Unit about cities and neighborhoods (e.g. _das Fachwerkhaus_, _das Hochhaus_)
  - The Unit also included a bit of new city-related vocabulary, but I quickly memorized it with some new flashcards

## ResourceRun

- Two weeks ago, I decided to take a (relatively) small break from programming due to being utterly burnt out
  as a result of the nation-wide WorldSkills tour
- Even though I've got a bunch of exams due, I started feeling well enough to resume work
- However, instead of picking up my latest active project [GoldenForge](https://github.com/RedGrapefruit09/GoldenForge),
  I decided to start a new one
- [GoldenForge](https://github.com/RedGrapefruit09/GoldenForge) is currently put off indefinitely
- The new project is called ResourceRun and is effectively a better version of my older project
  [Eggland](https://github.com/RedGrapefruit09/Eggland), now that I've gained more practical
  experience with game development
- To recap the game's concept:
  - There are 4 seasons corresponding to the ones in real life: spring, summer, autumn, winter
  - The map is procedurally generated and consists of the ground and objects like trees, rocks, ores etc.
  - You have an inventory with a basic set of tools to gather as many resources from the map as possible
  - You can collect materials in the inventory and upgrade & repair your tools
  - Every 5-10 seconds, a tile disappears from the edges of the map, making it an automatic TNT-run-like game
  - Your total score is determined by the resources you've collected
  - However, a good balance between time into resource collection and time into getting good tools must be met in order
    for an optimal result
- I've been working on this game in the time I could spare from my other activities
- Here are the main highlights of this week's progress:
  - Set up the project
    - Even in this early stage, it's already publicly available [here](https://github.com/RedGrapefruit09/ResourceRun)
      on GitHub
  - Created the generation of the ground
    - The tiles are made pretty around the edges (they have right, left, top, bottom, bottom-left etc. variants)
    - Instead of creating a `GameObject` with a `SpriteRenderer` for every ground tile, they are streamed at runtime
      into a pre-defined Unity `TileMap`
    - The ground `Tile` references are stored in a separate `ScriptableObject` for every season of the generation
    - The sprites for the grass I imported from the old project and tweaked to have the pretty edge cut-outs
  - Created the generation of world borders
    - Every border is represented by an automatically-created `GameObject` with a `BoxCollider2D`
    - Since the player's physics are implemented through a simple `Rigidbody2D` with no `gravityScale`, this results
      player being unable to go beyond the border
  - Added essential player movement:
    - Basic movement
    - Crouching/shifting using `LeftShift`/`RightShift`
    - Running/sprinting using `LeftControl`/`RightControl`
    - A stamina bar displayed in the player's HUD prevents the player from running indefinitely
  - Made the world generation code modular and easily extensible
    - The architecture is represented by a `WorldGenerator`, which has multiple responsibilities:
      - Starting the world generation
      - Collecting the generated objects in two groups: ones tied to a position, and all others
      - Cleaning the stuff generated by the previous pass before proceeding to another one
      - Invoking `GenerationStep`s
    - The `GenerationStep`s represent phases of the world generation, most notably borders, ground and objects
  - Added object generation for things like trees, ores and bushes
    - The `ObjectGroup` `ScriptableObject` contains data about a group of interconnected objects (trees, for example)
      and about all members of that group
    - The sprites for testing were imported from the old project as well
    - The `Season` `ScriptableObject` includes all _local_ `ObjectGroup`s to be generated during this season
    - The `ObjectGenerationStep` actually picks up on all the `ObjectGroup`s and generates them
    - Choosing `ObjectGroup`s to generate is based on a simple random number, whereas choosing the individual variant
      from that group is based on a _weighted list_ implementation (which I stole from StackOverflow)
  - Fully completed the set of objects for the initial spring season:
    - Trees
    - Ores
    - Bushes
  - Created the full inventory system (took a lot of frustration compared to the other systems mentioned here):
    - The items are displayed in an inventory HUD with slots
    - Every slot contains a certain amount of an item
    - The `Inventory` class manages all the slots internally, with operations like get; set; insert
    - An item can be selected from the inventory (it will be highlighted in the HUD) by pressing on it in the HUD
      or by clicking a number key that corresponds to its slot index (item 1 => `Alpha1`)
    - The selected item can be dropped onto the ground by pressing `Q`
    - Dropped items are animated and can be picked up once the player touches them
    - Every item has a tooltip, which will be shown for the selected item in a separate window when `T` is pressed

## Website

- This week, I renovated my website on GitHub Pages with [Jekyll](https://jekyllrb.com)
- The website has been up since early 2021, but served only one purpose: to host my Maven repository
  - This was needed to provide access to all of my modding libraries through [Gradle](https://gradle.org)
  - The URL is `https://redgrapefruit09.github.io/maven/`
- However, as described in the _Journaling_ section, I recently decided to set it up to host this newsletter
- The site is powered by a static site generator [Jekyll](https://jekyllrb.com) and hosted on GitHub Pages
- As of now, the contents of the site include:
  - This newsletter, powered by Jekyll's built-in blogging system
  - An article section for non-consistent article writing, I'm planning on publishing some new releases there
    in a week or two
  - An [About](https://redgrapefruit09.github.io/about/) page, that links to my finished projects and gives
    a brief description of the website
  - A homepage giving links to the newsletter, articles and Maven
    - I also messed with the [Liquid](https://shopify.github.io/liquid/) templating language here to display
      the latest newsletter post and article
    - Took a while to make, but I'm proud of it!
