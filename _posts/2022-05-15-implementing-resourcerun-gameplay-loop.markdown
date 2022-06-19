---
layout: post
title: "0.2: Implementing ResourceRun's Gameplay Loop"
date: 2022-05-15 +0300
---

## Journaling

- I wanted to make some clarifications in this status update about my journaling method:
  - Posts are released as a form of status updates
    - There is no schedule for releasing these updates and there will never be one
    - Though, mostly they are released every Sunday with breaks for a few weeks every once in a while
    - The posts are somewhat versioned (e.g. _0.1_):
      - The first number is the major iteration of the content format
      - The second number is the number of the post, relative to the first number
      - The second number is kept every major iteration
    - The main topic of the post comes after the version
  - The main target audience of the posts are:
    - People interested in my projects (these are essentially written dev-logs)
    - People interested in the contents of this website (articles, projects index etc.)
    - Myself trying to rewind on experiences, projects from a while ago
- The current (v0) content format consists of:
  - Headings for every major subject (_Journaling_, _Website_, _Project_, _German_ etc.)
  - Markdown bulleted-lists for structuring information:
    - The first level for summary points
    - The second level for key points
    - The third level for detail points
    - Deeper levels are used for highly-nested information, and should typically be avoided if possible
- Lastly, I want to bring up a few important points about this newsletter:
  - I don't guarantee to post here on a regular basis, however much I'd like to be
  - I don't guarantee to keep up a consistent content format (like this one)
  - I don't guarantee to maintain a certain length of posts (1000 words, 200 lines etc.). The length of these posts
    depends on what I have to tell and my willingness to write at that point of time

## German

- Lesson highlights:
  - Studied a bit (only nominative and accusative cases) of strong declension for _welcher_ and _dieser_
    - I already learned that from [GVY](https://germanveryeasy.com)
    - The topic is pretty easy, the strong declensions in the nominative and accusative reflect noun
      gender (except for accusative masculine), and the rest reflect the appropriate definite articles
      (_der Buch_ => _dieser Buch_, _dem Buch_ => _diesem Buch_)
    - I wonder if this is a preamble to strong adjective declensions, which work in the exact same way
  - Revised geography vocabulary with a text about living on an island called _Hallig_
  - Revised indefinite dative articles (_einem_, _einer_, _einem_) and possessive dative pronouns (_seinem_, _ihrer_)
    - This was a bit weird, since I had thought that we had already finished off the dative case, which was combined
      with two-way prepositions in this book
    - So, there was nothing new
  - Analyzed a few texts about room-tidying (_aufräumen_), which was rudimentary
  - Revised and finished off the two-way prepositions topic
    - To summarize, nouns after prepositions meaning movement use the accusative case, and after prepositions
      meaning state nouns use the dative case
    - I originally struggled a lot with this topic and just could not get it, but figured everything out a few
      months ago
    - We've already studied most of this topic, the remaining stuff are accusative-only and dative-only verbs
      and their equivalents (_liegen_ => _legen_, _stehen_ => _stellen_ etc.)
- Added and studied a bunch of vocabulary in Anki
  - Mainly important words from some of the texts, like _ziemlich_, _sauber_, _wieso_, _genauso_ etc.
  - It was pretty annoying to study, as, unlike most other vocabulary, these words are completely German-only
    and have no foreign roots (e.g. _der Apfel_)

## English

- I got back into my weekly English lessons due to a technical break
- The homework for the lesson consisted of:
  - A few vocabulary exercises on words I totally hadn't encountered before
  - A rudimentary writing task to practice the Future Continuous and the Future Perfect
  - Exercises for a
    new [TED talk](https://www.ted.com/talks/vishaan_chakrabarti_how_we_can_design_timeless_cities_for_our_collective_future/transcript)
    about modern city design. They were mostly discussion-related, and I only needed to make notes
- As always, I made a _few_ notes on the talk, only 5 pages, nothing special
- On the actual lesson, we discussed the talk and revised, once again, the Future Continuous and Perfect

## ResourceRun

- Preface:
  - This week was highly productive for the ResourceRun project, despite a lot of exams and generally a lack of time
    (I was only able to productively work on it for 3 or 4 evenings)
  - Though, in the limited time I had I went from only having the barebones (and buggy) inventory system to
    (almost) all major gameplay loops being fully implemented
  - Next week, I'm hoping to finish the few remaining pieces of gameplay and start working on the other three seasons
    (summer, autumn and winter) with all the art, configuration and code required
- Fixed a bunch of bugs with the inventory system
  - Fixed an issue in the drop code, which glitched the inventory's internal state and allowed the same item
    to be infinitely dropped and duped
  - Fixed the `_selectedItem` variable (reference to the currently selected item) being out of sync with the
    actual item at the `_selectedItemSlot`
    - I first implemented this by just updating the value every `Update` (tick), but it was inefficient
    - I then figured out the actual contexts when the value actually gets out of sync and started updating
      it only there lazily
  - Fixed the tooltip for an item being shown when the item it's for is no longer selected or no longer exists
    / is in the inventory
  - Fixed `DroppedItem` instances sometimes being invisible by changing their order in layer in the `SpriteRenderer`
- Made lots of improvements to the inventory's backend code
  - Reorganized and cleaned up the inventory code (`#region`s)
  - United the inventory code with the player's code
    (`Inventory` on a system object => `PlayerInventory` on the player's object)
  - Made `DroppedItem` instances de-spawn, destroying themselves and the bound `Item`, after one minute of being
    not picked up
  - Refactored ancient inventory code to be more readable
  - Re-bound buttons for selecting inventory slots from the HUD to the new method target
  - Removed the approach of the gross `testItem` property in favor of having a `GameObject[] startupItems` to be
    automatically given out to the player once the game begins (the list currently consists of a bronze axe and
    pickaxe)
  - Started compacting together duplicate items in the inventory, when possible (2 bronze and 3 bronze with
    `maxCount` >= 5 get combined into a single item)
  - Added a _shift-back_ operation to the inventory that shifts all items after a given slot backwards by a single
    inventory slot
  - Added a _compress_ operation based on _shift-back_ that packs together all items to the left of the inventory
    and compacts together any compatible items
  - Added an _extract_ operation that extracts a set amount of a given item, using the passed item only as a
    reference for comparison
  - Added a _count-of_ operation that counts the amount of a given item in the inventory, once again using the
    passed item only as a reference
  - Created a united API for a bunch of repetitive utility code for working with items in the `Item` class:
    - `Item.Same` and `Item.Different` equality operations (`Item.Different` is `!Item.Same` under the hood)
      that compare whether both references point to `null` or if they both point to an item with the same
      `label` (type)
    - `Item.Create` for instantiating and initializing an `Item` instance from a prefab `GameObject`
    - `Item.CreateAndInsert`, which calls `Item.Create` and also inserts the newly created item automatically
      into the given inventory instance
    - `Item.Drop` that de-initializes the given `Item` instance and creates a `DroppedItem` on the ground
      at the given position, pointing to the hidden `Item`
- Completely reworked the backend for item tooltips and improved them
  - The old backend was basically only an abstract method in the `Item` class for creating the tooltip that
    returned a plain `string`
  - The main problem with that was that it required a lot of string concatenation (or `$""`) and messy code for
    anything beyond a single static line (e.g. tool and resource tooltips)
  - The new backend works based on an `ItemTooltip` class, which is a wrapper for `System.Text.StringBuilder`
    and returns the built `string`. This allows for a fluent API for appending lines to the tooltip without
    messy or repetitive boilerplate code
  - The API for calling the method is wrapped in a `GetTooltip` method that handles the `StringBuilder` and
    `ItemTooltip` creation in the background
  - Afterwards, I ported all the old tooltips to the new system, which was a little bit painful
  - I also tweaked the tooltips' content a little: the ones for tools contain their durability in the
    `current/max (percentage%)` format and their efficiency, and resources contain their per-unit worth
- Implemented the gathering system
  - The stats (efficiency multiplier and durability) plus the constants for calculations are stored in the
    `ToolItem` class and displayed with a tooltip (see above)
  - There are two animation methods for the gathering process:
    - Overlay (bushes and trees). Takes a per-frame `Sprite[]` from a sprite atlas containing overlay sprites
      and gradually puts them on top of the gatherable, then finishes
    - Fall (trees). Gradually rotates to the left on the _Z_ axis until reaches `-90f` degrees, then finishes
  - The animation, loot and tool durability code are handled by the `Gatherable` class, attached to all
    "gatherables" (trees, ores and bushes)
  - Whether the player can reach out to a gatherable is checked by a `PlayerTrigger` system, that captures the
    object in the trigger (`null` when nothing) if it matches the given predicate (`Func<GameObject, bool>`)
  - The code that triggers the gathering process is handled by the `PlayerGathering` class
  - The delay between switching in rotations or overlay frames is dynamically calculated, based off of the used
    tool's efficiency multiplier
  - The tool's durability is used up every time a gatherable is broken
  - The tool is animated on the side of the `ToolItem` class with programmatic rotation
  - The player can't move or select other items in their inventory while the gathering process is taking place
- Implemented the world fade system
  - As more world-related code got implemented, I decided to move the generation-specific parts into a separate
    directory
  - The fade process is internally invoked and suspended from the `WorldGenerator` class on generation end and
    start, respectively
  - The fade effect essentially computes the map edges and all edge positions and removes tiles at those edge
    positions with a delay, which looks really cool
  - This is the gameplay mechanic that prevents the player from permanently camping on a single world layer
    (season)
  - At this point, I also added some missing "alone" sprites to the grass sprite atlas for spring, as the existing
    ones didn't account for a few special scenario
  - The toughest task in this entire system was recomputing the sprites of the deleted tile's neighbors
- Added the resource management system
  - Imported and tweaked resource sprites from the old project. In total, the game has nine resources
  - Each resource has a per-unit worth value stored in a special `Item` subclass - `ResourceItem`
  - That worth value is displayed in the item's tooltip after the primary line
  - To accommodate the effect of loot being dropped from gatherables, I created a loot table system:
    - The `LootTable` `ScriptableObject` contains a set of `LootTable.Entry`s, each containing the item's `GameObject`
      and the min and max amount of that item to be dropped
    - The `LootTable` class itself implements a `Generate` method that generates the contents of that `LootTable` around
      a given `Vector3` position with a set min/max spread
    - The `ObjectGroup` `ScriptableObject` was also modified to associate a separate `LootTable` for
      every `ObjectVariant`
    - The `Gatherable` class is also responsible for invoking `LootTable.Generate` after everything is done
  - Lastly, I squashed a few minor bugs:
    - Fixed `LootTable.Generate` aborting when only one `Entry` returns `amount=0`
    - Fixed a `NullReferenceException` being thrown in an edge case when gathering

| Resource | Type | Worth |
|-|-|-|
| Bush Leaf | Other | 5$ |
| Bronze | Ore | 15$ |
| Coal | Ore | 20$ |
| Wood | Other | 25$ |
| Iron | Ore | 40$ |
| Diamond | Ore | 65$ |
| Emerald | Ore | 90$ |
| Ruby | Ore | 120$ |

- Lastly, I implemented the large upgrade system
  - Added some UI sprites and created the UI ([screenshot]({% link cdn/20220515/RRUpgradeUI.png %}))
    - The output item's `label` is displayed on the top
    - In the middle, all ingredients for the upgrade are displayed with:
      - The item's icon
      - The item's name
      - The status (_collected/required_) of the collection process
    - The status is also visually represented by a color scheme:
      - Green if the requirement is met
      - Yellow if the requirement is partially met
      - Red if the requirement is not met
    - At the bottom the actual _Upgrade_ button is located, it turns to green when all requirements are met and
      functions only then
  - The upgrade data is stored in the `Recipe` `ScriptableObject`:
    - The ingredients, which contain the item prefab and the required amount of that item
    - The input item prefab
    - The output item prefab
  - The recipes are dynamically (and lazily using internal state management) fetched for the item that is currently
    selected
  - If the player isn't holding an item or if there isn't a recipe that has the item being held as the output,
    an issue message will be displayed in the UI box, while all the content will be hidden
- Tweaked the game's balance for:
  - `ObjectGroup` frequencies
  - `ObjectVariant` relative weights
  - `Recipe`s
  - Tool statistics (durability and efficiency multiplier)
- Added an occupation system for world generation, that allows an object from an `ObjectGroup` to occupy more than
  one position
