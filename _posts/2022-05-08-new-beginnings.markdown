---
layout: post
title:  "New Beginnings"
date:   2022-05-08 +0300
---

## Journaling

- On May 12th this year I temporarily stopped journaling. This was for a variety of reasons:
    - The preparations for WorldSkills (more on that in an article coming soon) exhausted my time and energy
    - The technique I used was horribly inefficient, requiring me to spend about an hour every day writing up a long rant
    - It started seeming pointless to me, because I was unable to share my hours of work with anyone else
- Since then, more than 1.5 months have passed and the distraction (WorldSkills) has gone away, so I decided to come
  back to consistent journaling
- But, I decided to make some major changes:
  - Instead of trying to pump out a post every day, I decided to starting making posts every week on Sunday
  - The purpose of the posts had to shift to just be a method of capturing information, not a productivity app
  - For productivity, I returned to the trusty old [Trello](https://trello.com) app, allowing me to effectively
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

## Studying

- I have a ton of exams planned for the next two weeks, so I've been sitting in my [Trello](https://trello.com) chores
  board this week for hours on end
- We haven't studied much new stuff, just tons of revising and bare study
- In late May, we're also going to switch buildings often, which, obviously, is neither convenient nor easy, so
  I don't expect there to be much pressure
- Some major highlights:
  - Did the History test at home with tons of detail put into it
  - Polished and finished the [Scratch](https://scratch.mit.edu) school project
  - Updated the description file for the Scratch project as well
  - Completed a Biology project on a family of flowers, was annoying to do due to a severe lack of sources
  - Spent a while adding Literature theory for the exam into Anki
  - Banged my head against the desk trying to memorize a tough poem with zero classic interconnection

## German

- Finished migrating my entire German collection of vocabulary from Obsidian to Anki flashcards
  - It all totalled in about 850 flashcards
  - That's not really a lot, considering I haven't even added all the words from the glossary, only major highlights
- Relearned and revised all this past vocabulary, refreshing some older topics in mind
- Ported all my theory for grammar as well, which was a tad bit more painful to accomplish
  - My main reference source for German grammar is [this excellent website](https://germanveryeasy.com)
  - I decided to rework my notes in the process of porting them, so I did everything from scratch
  - Plus, I added a bunch of new theory on some other topics I wanted to study prematurely
  - Lastly, I re-studied all the older grammar just to make sure I haven't forgotten anything important
  - I don't know why I like (most of) German grammar so much, maybe I'm just a masochist
- Highlights from the lessons:
  - I had a test on the past 6 Units, combining all the vocabulary and grammar concepts from the past 3-ish months
  - Half of the test we did on the lesson, the rest I pushed myself through in the homework
  - The test wasn't hard, especially after my recent migration to flashcards I had zero problems with the vocabulary
  - Then I started a new Unit about cities and neighborhoods, which didn't have much new vocabulary or grammar concepts

## ResourceRun

- Two weeks ago, I decided to take a (relatively) small break from programming due to being utterly burnt out
  as a result of the nation-wide WorldSkills tour
- Even though I've got a bunch of exams due, I started feeling well enough to resume work
- However, instead of picking up my latest active project [GoldenForge](https://github.com/RedGrapefruit09/GoldenForge),
  I decided to start a new one
- [GoldenForge](https://github.com/RedGrapefruit09/GoldenForge) is currently put off indefinitely (it's currently a bit
  pointless) in favor of game development
- The new project is called ResourceRun and is effectively a better version of my awful project
  [Eggland](https://github.com/RedGrapefruit09/Eggland) (yes, the name is very cringe) after I've gained so much
  experience with competitive game development
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
  - Set up the project. It's already publicly available [here](https://github.com/RedGrapefruit09/ResourceRun) on GitHub
  - Created the generation of the ground. The tiles are made pretty around the edges of the map and are also streamed
    automatically into a Unity TileMap for better performance with bigger map sizes
  - Created the generation of world borders (GameObjects with simple BoxCollider2Ds), preventing the player from going
    off the map
  - Added player movement with shifting, sprinting and a stamina bar
  - Made the world generation code modular and easily extensible
  - Added object generation for things like trees, ores and bushes
  - Fully completed the set of objects for the initial spring season
  - Created the (pretty complicated) inventory system, which looks simple but took an unreasonable amount of time
    to figure out the architecture of and fully implement
