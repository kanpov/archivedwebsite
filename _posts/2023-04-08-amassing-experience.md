---
title: "2.15: Amassing Experience"
date: 2023-04-08 +0300
excerpt: "My journey towards learning 3D has taken various unexpected (and incredibly time-consuming) twists and turns..."
---

## Preface

Due to an incredibly busy holiday period in February, I was entirely unable to write a new post in spite of the massive
amount of work I'd been able to show off even then. So, I've finally reappeared out of obscurity after more than 3
months since the release of NL1.14 and am ready to show off the 4 large multi-week projects that I have completed since
January. In reality, there's also a fifth project that is nearing completion (a restaurant scene), but, since it's still
partly incomplete, I've decided to omit it from this post and instead cover it in NL2.16.

My journey towards learning 3D has taken various unexpected (and incredibly time-consuming) twists and turns in the
past couple of months. My work has morphed from the single-week small ventures that I showed off in the last post into
large monolithic  projects that each consume 2-4 weeks of active development time.

The aforementioned change in the structure of my work is largely motivated by the fact that I've managed to go way
further in my assignments than anybody in my competition, and, therefore, have started receiving individualized 
assignments and doing my own personal projects that are no smaller. In this post, I'm going to break down all of these 4
projects in detail and explain the whole process and, admittedly, the mistakes I made (and, hopefully, learned from)
along the way.

I also wanted to mention that my attempt at  reintroducing [jrnl.sh](https://jrnl.sh) into my daily routine
unfortunately failed due to the reappearing issue of time constraint. Once again, I fell into the trap of high
expectations and a practically unending chunk of time (e.g. the holiday season) to fulfill them, and, as soon as that
time budget ran out, I had to drop the experiment. I should've been a lot more careful with such initiatives to begin
with, though this was yet another show of the effects of a "hardliner" approach towards scheduling.

Lastly, as you may have already taken notice of, the format version of the journal has received a bump to 2, a change
that was primarily motivated by my realization of the ineffectiveness of bullet-point lists for this newsletter. As I
was writing a draft of this post back in February, expecting to be able to push it out by the end of the holiday season,
I encountered a roadblock: my bullet points, which I'd sworn by for years as an incredibly convenient essay format,
were getting a lot bigger and trying to separate the text of one bullet point into several others hastily became an
annoyance, so I decided to simply drop the entirety of that formatting style.

## Project I: Farm

### 1. Concept

Essentially, each one of my assignments has a similar format (at least on my design front, since the work also
involves a programmer with their own technical requirements): I'm given an overall theme and a minimal set of models
to create. This gives me a great opportunity for creativity, though making it hard to amass a clear vision of the
project from the very beginning. The contrast to this were my previous competency's assignments, where everything was
written about in exhaustive detail over the span of 20-30 pages (or more), so it took quite a decent chunk of time to
get used to these open-ended tasks.

The concept for this project was one of my first assignments after the release of NL1.14, which involved designing a
relatively low-poly scene for a farm game. I was given this non-promising minimal set to work with: tomatoes, pumpkins,
corn, carrots, milk, a tractor, a house (supposedly, a farmhouse, though I went with a different design in the end), 
some place where the aforementioned plants would reside, cows and chickens.

After gathering some references from open 3D sharing mediums (which I, seemingly, erased from the project folder
afterwards, although I usually try to do the inverse), I began composing and modeling the scene.

### 2. Modeling and Composition

In terms of style for this scene, I used two major workflows for the modeling process. For the hard surface objects,
such as the house and tractor, I used a standard semi-minimalistic low poly workflow with two bevel layers: the stylized
edge and vertex bevels to basically mimic a low poly sculpt without actually doing any sculpting and the three-segment
edge bevel on the whole mesh to slightly soften the hard low-poly edges. For the organic objects that I found much less
intuitive to model, such as the fields, crops and animals, I used a smooth subdivision workflow without adding many
imperfections that are largely unnecessary in a scene that is supposed to be reasonably minimalistic.

While modeling the objects was certainly time-consuming, what felt even more infuriating was the scene's composition.
While working on compositions, I often tend to behave like a perfectionist, infinitely scaling up and down, moving and
rotating the objects in the scene until I'm finally satisfied with the result. My lack of proper knowledge in
composition makes me constantly critical and disappointed by the quality of my work, which, on the positive side,
promotes effective and beneficial iteration and, on the negative side, is a strong burden on my motivation to continue.

In the end, I think I did a somewhat decent job of the composition and overall structure of this scene, which, as much
as I'd like to put it otherwise, can't be said about the latter parts of the process.

![Full modeling and composition without cavity shader](/cdn/20230408/Farm_2.png)
![Full modeling and composition with cavity shader](/cdn/20230408/Farm_1.png)

### 3. UV Unwrapping

Before and during the UV unwrapping process for this scene, I made various mistakes which would severely hinder any
further growth of this project.

Firstly, I didn't retopologize this scene: for a bit of context, retopology is a process that is necessary to create a
low detail (low-poly) version of a high poly object/scene in order to win over performance and ease of development,
while still technically retaining the detail of the original high detail (high-poly) version by baking it into the
normal map (not going to go into much detail on what baking is since it is a highly technical and complicated topic
that I don't have the proper knowledge to talk about). This scene weighed around 1.05 million triangles with the
(in hindsight, pretty overkill) three-segment bevels, exponential subdivision and so forth, and desperately needed a
rework before proceeding with UV unwrapping, in spite of which I proceeded onwards.

Secondly, I used automatic UV unwrapping for almost the entirety of the project, not realizing how much it'd ruin my
textures afterwards. This meant that the seam placement was automatic, resulting in tons of stretched and overlapping
islands, that the margins between islands were too big, resulting in tons of tiny UV islands being spread around, and
that iterating on the maps was incredibly difficult, since rerunning this _"Smart UV Project"_ algorithm on a 300K+
triangle object takes several minutes and is only executed on a single CPU thread. And even in places where I had enough
brainpower to place my seams manually, the algorithm would simply overwrite them with a noticeably worse placement, and
I didn't even know that was a thing.

Lastly, even though I did the texture set separation reasonably well, splitting the scene into "Foundation" (monolithic
ground objects), "Organic" (plants and animals), "House", "Fields" and "Tractor" (all self-explanatory), I didn't use
a proper UV packer to squeeze out more texture space utilization, instead relying on Blender's default (and, admittedly,
quite outdated) tooling to do so. This is a mistake I'd only fix in project V after I'd learned about 3d-io's free,
fast and simple UV-Packer addon. It's fair to say that, at this stage, my understanding of a proper unwrap was severely
lacking.

### 4. Texturing

As for the textures, I first started creating highly realistic PBR maps using the default materials in Substance Painter,
though relatively quickly realized that such an art style will not nearly fit the scene I'm trying to achieve, so, when I
was about halfway done, I had to entirely restart and try to source the materials from:

- Free PBR texture websites, like _free-textures.com_, from which I downloaded all the correct maps and re-assembled
  them manually into a fill layer. This wasn't the greatest method of assembling materials, but, when there was no
  other option, I opted for such a workflow.
- Substance Community Assets (formerly known as Substance Share), which provides a pretty small (~1000 items in total)
  collection of compiled Substance Designer materials (`.sbsar` files).
- Default smart materials, which I tweaked and deleted layers from to make them look more stylized.

Overall, the process consisted of gathering data from these sources and tweaking everything until it looked relatively
decent. I wouldn't say this is a great texturing job, but it was more than enough for the requirements of this specific
assignment:

![Texture POV 1](/cdn/20230408/Farm_3.png)
![Texture POV 2](/cdn/20230408/Farm_4.jpg)

### 5. Finalization

After exporting the 5 texture sets in 4K to the formats that Unity's Universal Render Pipeline (URP) uses, which include
albedo-transparency (color), normal, roughness and metallic-smoothness (metallic) maps, I brought the assets as `.fbx`s
into the game engine and re-applied the textures, getting a result that hardly deviates from the previews shown back in
Substance Painter:

![Unity POV](/cdn/20230408/Farm_5.jpg)

## Project II: Axe Object

### 1. Concept

The entire concept of this assignment was not my own, but rather I had to follow Grant Abbitt's absolutely excellent
tutorial series ([available on YouTube here](https://www.youtube.com/playlist?list=PLn3ukorJv4vvDHfsQCACI3qVgdAMfP3-7))
on creating a highly detailed game-ready axe in Blender.

The main motive behind following along was for me to learn the basics of sculpting, a skill that I'd never attempted to
delve into prior to beginning this project, and see what the proper game-ready asset/scene workflow really looks like
(with, unlike project I, all steps completed) on a practical example. Recreating the entirety of this artwork took me
around 2-3 weeks with breaks caused by me getting infuriated during sculpting, although this project turned out to be
the most presentable out of all I'd worked on prior.

### 2. Sculpting

After I'd created an initial low-poly blockout for the main objects (which was the first, though somewhat unremarkable
phase of this entire process), I began gradually sculpting out details for each one of the components of this axe,
thereby slowly but surely building up an incredibly refined level of detail on the model. In order to break down the
workflow for sculpting out each component, I'd like to cover them individually.

![Axe handle POV 1](/cdn/20230408/Axe_1.png)
![Axe handle POV 2](/cdn/20230408/Axe_2.png)

Firstly, by far the largest and the second most visible component of this axe is its handle, shown on the screenshots
above with the cavity shader enabled. This component was the most painful to sculpt for me, as the elements where the
author of the tutorial dug in to create refined wood details were a lot more difficult for me to recreate without a
proper graphics tablet, whose pen would control the stroke's radius and intensity in Blender automatically. Despite
these hurdles and the fact that my result here looked noticeably different from Grant's, this handle turned out to
be reasonably presentable when combined with the other components that, for the most part, effectively overshadow
the handle's negatives.

![Axe POV 1](/cdn/20230408/Axe_3.png)
![Axe POV 2](/cdn/20230408/Axe_4.png)

Secondly, the component I'm most proud of in the entire mesh is the axe itself (shown above). The sculpt for this
component was so complex that it's easier to divide into multiple layers. The first layer consisted of refining the
low-poly blockout to accurately reflect the hard-surface, yet at times quite smooth shape of the component and
fixing various artifacts after voxel-remeshing. The second layer consisted of adding the runes to the axe's central
cut-out and refining them, and digging in with various curved lines, cut-outs and medium-sized details. The last
and by far the most time-consuming third layer consisted of overlaying a noise texture atop the runes, adding tons
of tiny imperfections, scratches and small details all over the model.

![Upper straps POV](/cdn/20230408/Axe_5.png)
![Lower straps POV](/cdn/20230408/Axe_6.png)

Thirdly, the somewhat less detailed components of this mesh were the upper straps (first screenshot above) and also
lower straps (second screenshot above) that had more leather-like and organic shapes. The upper straps were to be
attached to the upper part of the axe's handle and are essentially the connector between the handle and the axe
itself, and had a cross-like shape that I refined further with dig-ins, scratches and holes, though the part that
made the straps look much more visually appealing was the clay brush, which I applied on top of almost the entire
component (in slight deviation from the author's result). The lower straps had a pretty simple cylindrical shape
with dig-ins that got its high-poly detailing from the same clay brush (works like magic on some types of objects).

![Rings POV](/cdn/20230408/Axe_7.png)

Lastly, the two rings attached to the very bottom of the axe's handle didn't receive much attention in terms of
sculpting: except for the basic smoothing, the torus-like shapes were only slightly altered with the addition of
holes and scratches, though these objects would hardly be the focus of attention in the final result, so this was
certainly justified.

Combined together, these sculpted components look like this with cavity shading enabled:

![Full axe POV](/cdn/20230408/Axe_13.png)

### 3. Retopology

Combined into a single mesh, these high-poly axe components present a polygon count of 4.187.640 triangles, an
unacceptable amount both from a performance and a UV unwrapping perspective, therefore I needed to thoroughly
retopologize these components. Thankfully, I had duplicated and saved the blockout low-poly models of each
component before proceeding onwards with sculpting, which eased the retopology process by giving me a massive
 head-start.

The axe itself didn't request many changes from its blockout, aside from correcting the topology of the central
cut-out, thereby converting it from a massive N-gon (a planar shape with more than 4 vertices, which makes for
a hefty amount of problems during unwrapping, sculpting, rigging etc.) to a large set of quads (polygons).
For the handle, I removed unnecessary faces that wouldn't be visible and then manually wrapped each vertex as
well as possible around the high-poly mesh using Blender's Shrinkwrap modifier and Snapping tools. The workflow
for the lower straps was vertex-snapping too, though I decided to entirely recreate the upper straps, as the
initial blockout matched terribly with my high-poly result. The torus-shaped rings didn't request any major
changes, so I left them as is. Here are the results:

![Non-transparent wireframe view of the axe low poly](/cdn/20230408/Axe_8.png)
![Solid cavity-shaded view of the axe low poly](/cdn/20230408/Axe_9.png)

### 4. UV Unwrapping

Before unwrapping the mesh, I needed to go through the incredibly tedious process of deleting unused parts of
each low poly component, matching the vertices that mark transitions from one component to the other together
perfectly 1:1 and finally joining the components together to create the final manifold low-poly mesh with
5.473 triangles.

The UV unwrapping techniques that had been presented in the series itself were, for the most part, not
applicable to my mesh's geometry, so I did the seam placement manually and thereby got a much better UV island
setup in comparison to the author's. Although, some parts needed a few more seams, but the ~10-20% stretching
in these areas didn't meaningfully reflect whatsoever on the textures. Once again, using Blender's built-in
UV packer was a mistake, and I made the margin between UV islands too large, not accounting for the fact that
I'd have a 4096x4096 on the textures, for which only a 0.02 or lower margin is actually necessary to eliminate
color bleeding. Here are the final seams and islands that I landed on before texturing:

![Screenshot with seam placement and baked UVs](/cdn/20230408/Axe_10.png)

### 5. Texturing

The baking, PBR texturing and painting parts of this series were by far the worst developed, which is not
necessarily the author's fault, but rather that Blender's tooling is unbelievably poor and almost ancient in
those areas: baking tools are unintuitive, undeveloped and lack any ability for debugging matching errors when
between high and low poly mesh when baking normals from one to the other, PBR texturing is practically
non-existent with only a barebones node setup available to work with and texture painting is quite basic as well.

The aforementioned problems led me simply to switch over to baking and texturing all in Substance Painter, which
resolved all the issues I'd been experiencing with baking normals ceasing to function in Blender and made the
entire process so fast that I was able to do what the author spent 6-7 hours on in a matter of 1-2 hours, and
get a much more realistic and presentable result. So, the texture setup is ruined steel for the axe, more
perfect black steel for the rings, stylized-ish wood for the handle and tweaked leather for the straps, which,
in spite of its simplicity, looks like this:

![Axe textures in Substance Painter, view 1](/cdn/20230408/Axe_11.png)
![Axe textures in Substance Painter, view 2](/cdn/20230408/Axe_12.png)

## Project III: Monopoly

### 1. Concept

This project was another template-style assignment similar to project I (the farm), though the theme this time
was measurably more specific and somewhat more restrictive in comparison: a monopoly simulator. The game itself
and the rules thereof need no introduction, however the choice I faced when designing the concept for this
project was quite unique: I could either recreate the game board on a cramped tight grid to most accurately
mimic the original board game's appearance, or I could try to do something more novel and recreate the concept
in proper 3D space. Here's the board game as reference to better understand what I'm writing about:

![The original game's board](/cdn/20230408/Monopoly_0.jpg)

The latter idea had me perplexed on the exact design and certainly would be a massive challenge to flesh out
properly, but what I disliked more was the first option, which seemed only like a quick and dirty solution that
was neither innovative nor "truly 3D", so I went with a custom design. After contemplating for a while and
unsuccessfully diving into the Internet looking for ideas, I settled on a large 3D board, 3D figures on each
cell of it and generally various "no compromise" models.

### 2. Modeling and Composition

So, after nailing down the concept, I started working on the models, and the first sign of progress I had was
the modeled structure of the game, which I altered significantly in contrast to the original board game, as shown
on the screenshot below. The game's figures themselves would be located on top of the large 3D grid, whose cells
get larger as they get closer to the edges (this decision was motivated by the need to show the grid as not flat
and prevent the large skyscraper figures in the middle cells from being hidden/overshadowed by the figures on
neighboring cells). After I'd realized that the player models would simply not fit on the grid, I made a smaller
and lowered pathway in the middle, atop which these models would move alongside their currently corresponding
cells on the larger grid. And, inspired by the logo in the center of a Monopoly board, I modeled my own non-flat
version thereof.

![The models representing the game's structure](/cdn/20230408/Monopoly_1.png)

As for the figure layout, I settled on a smaller set of cells that relatively accurately represent the most
notable figures (cells) of the original game:

- 5 types of urban and suburban housing (blocks of flats, "generic" housing, more modern semi-detached designs,
suburban houses and more), overall 15 cells occupied thereby
- Minimalistic airports that occupy 2 cells
- Treasury chests with rewards that occupy 3 cells
- A "Go" sign, an arrow, a jail and a parking lot that occupy the 4 edge cells
- 4 types of skyscrapers inspired by modern designs, each occupying a single cell
- Question marks that indicate an unknown reward or punishments, occupying 3 cells
- Dollar signs that indicate a requirement to pay taxes, occupying 2 cells

In total, there are 32 cells on the board, to each of which I tried to give a decent amount of detailing that was
further enhanced with edge bevels, although the low-poly minimalistic style that was enforced by heavy time
constraint is still quite noticeable. Among the other models that are present in the scene, there is the
aforementioned circular surface, atop which the player figures would walk, those figures themselves, the dice
model (whose roll, supposedly, would be animated if these models were to be used in the production of the actual
game) and the sign. Overall, I was more than satisfied with the state of the scene at this stage, and the result
turned out to be much better than my initial expectations would suggest. Some of the key angles of the scene are
shown as screenshots below, with cavity shading enabled to highlight hard edges and bevels:

![Modeled scene angle 1](/cdn/20230408/Monopoly_2.png)
![Modeled scene angle 2](/cdn/20230408/Monopoly_3.png)
![Modeled scene angle 3](/cdn/20230408/Monopoly_4.png)

### 3. Retopology

The hard-surface non-optimized version of the scene presented above consists of around 600-700 thousand triangles,
and, in order to retopologize it into a highly optimized 20-30 thousand triangle scene, I used a variety of different
techniques: removing bevels and exponential subdivision, dissolving unnecessary or virtually indistinguishable
geometry, reducing the quality (amount of geometry) of text and curved objects, deleting various details that baking
normals would easily reintroduce and even manually recreating some of the objects, which were created in such a
destructive (e.g. irreversible) manner that rolling them back to a lower quality would be more complicated. As a
result, I got the scene down to 23.876 triangles, which is incredibly low given the capabilities of modern hardware,
making me question whether optimizing so much was an objective necessity.

![The solid view of the optimized scene](/cdn/20230408/Monopoly_5.png)
![The wireframe (raw geometry) view of the optimized scene](/cdn/20230408/Monopoly_6.png)

### 4. UV Unwrapping

As for the unwrapping, I'd managed to learn from my previous mistakes and did the seam placement manually with almost
no stretching entirely, however I still didn't use a proper UV packer, therefore getting suboptimal results and large
empty spaces. For this scene, I settled on only using 2 texture sets: one for the figures atop the 3D board and the
other for everything else (e.g. the board itself, the player figures, the logo and more), which worked out quite well
even with 2048x2048 (2K) textures later on. Below the UV seams (dark red edges) and islands are shown for each one of
these texture sets:

![UV seams and islands for texture set 1](/cdn/20230408/Monopoly_7.png)
![UV seams and islands for texture set 2](/cdn/20230408/Monopoly_8.png)

### 5. Texturing

Even though I spent several days trying to perfect the textures for this scene, the result still turned out quite badly
due to a variety of issues that I neglected during the texturing process: stylization (the scene was way too realistic
for a board game simulator), inconsistency in color choices, a general lack of attention to detail and at times even
incorrect materials. At first glance, the scene does look decently presentable, but upon further inspection large design
issues can be taken notice of, so I hope that this experience serves to teach me to make better stylized textures in the
future.

![A preview of the textured scene in Substance Painter](/cdn/20230408/Monopoly_9.png)

## Project IV: Recreating a Classroom

### 1. Concept

The background for this project was unlike the preceding ones, because initially it wasn't even supposed to have anything
to do with 3D art whatsoever: I received a creative assignment for geometry class, where I had to team up with several
other people to create an informative, yet highly artistic poster that would feature an in-depth explanation of a certain
topic, in our case, parallel lines and various theorems and axioms related to them.

Many of our competitors were incredibly skilled at both traditional and digital 2D art, hence why I decided that, in order
to truly bring something innovative to the table, we would integrate 3D art into the poster. The idea seemed relatively
manageable at first: I would recreate our geometry classroom in 3D space as photorealistically as I could, and my partners
would draw two different 2D posters, which I'd project somewhere in the scene, render everything out to an extremely
high image resolution and print the result on glossy A1 (594x841 mm in dimensions, 1:√2 side correspondence) paper.
However, the further I dug into this never-ending rabbit hole, the more I realized how mind-crushingly difficult it would
be to make this idea into reality in under 2 weeks. Due to privacy concerns, I'm not going to cover or show the work of my
partners in this post, and any appearance of it in embedded imagery will intentionally be blurred or blacked out.

### 2. Modeling and Composition

Before I would be able to begin modeling, various other decisions had to be made. Firstly, we settled on two flat posters 
that would individually be projected atop the e-board and regular marker board in the classroom. Secondly, I made a blockout
of the room in order to approximate and as exactly as possible calculate the area of the paper that the boards would occupy
in the final printed result; deciding on the correct 3D:2D space ratio was no easy task. Lastly, I had to ask our
teacher for a favor and take (with a good amount of help from my partners) dozens of close-up and zoomed-out photographs of
the room in order to capture every single detail I'd need to recreate several times. And only after all that and a modest
amount of coordination was I finally able to get to working on my own part.

With exception of sills, some chair parts and soft details, the vast majority of this equally vast scene consisted of
hard-surface models, for which I used the corresponding workflow with a slight amount of bevels. In total, the scene's
models could be non-formally divided up into various groups:

1. The students' chairs and tables, which I created with as much attention to detail and proportion as possible, since these
objects would occupy a large chunk of the final render and would most likely be the first focal point of a viewer's eye
when looking at the printed paper.
![](/cdn/20230408/Classroom_1.png)
2. The teacher's desk and the objects on top, with the chair and storage behind it. These objects would take up a reasonable
chunk of space on the paper and would be located in the bottom-left corner.
![](/cdn/20230408/Classroom_2.png)
3. The frontal and right walls, on which the hand-written board, the e-board and a bunch of other miscellaneous objects like
an electronic clock are located. The frontal wall would occupy a 50-60% chunk of the paper, so would later receive
much-needed attention.
![](/cdn/20230408/Classroom_3.png)
4. The left wall with the windows, heating and heat pipes, which, in the final version of the render, wouldn't be visible,
but still received a lot of time and attention.
![](/cdn/20230408/Classroom_4.png)
5. The back wall with the large storage system that wouldn't be visible at all, yet still received a fair amount of effort.
![](/cdn/20230408/Classroom_5.png)
6. The ceiling, which I didn't spend much time on and would be hidden, and the only reason for its existence was to have
the sort of "checkmark" that I recreated the absolute entirety of the classroom.
![](/cdn/20230408/Classroom_6.png)

### 3. Retopology

The high-poly no-compromise version of the scene that was partially shown above consisted of approximate 1.36 million
triangles, which, in a competitive scenario, would be an absolute nightmare to optimize, but, since I was aiming for a
full-on photorealistic scene and had powerful hardware that could handle such a toll on geometry, I only somewhat lightly
optimized the scene to the point where I'd be able to relatively effortlessly unwrap it. I only removed all bevels that
would noticeably complicate seam placement, decreased subdivision levels where it wouldn't significantly alter the overall
quality of the scene, yet didn't apply any aggressive optimization techniques or focus on the scene's triangle amount
(unlike during project III's development), so the result was still a pretty heavy ~861 thousand triangle scene (only
a ~37% improvement), which I was content with. A rather wide angle of the optimized scene is given below:

![A non-shaded solid view of the optimized scene](/cdn/20230408/Classroom_7.png)
![A wireframe view of the optimized scene](/cdn/20230408/Classroom_8.png)

### 4. UV Unwrapping

Since the entire motive of this project was not to compromise on any detail or quality, I applied that technique when
unwrapping the scene. The seam placement was, once again, done entirely manually in Blender (although I briefly
considered and rejected the idea of using Maya for UVs) and the unfolding was also done using the built-in tooling,
but the later stages of the process were partly automated. I went full-quality with dividing the objects into texture
sets and ended up with 11 of them, each containing a chunk of the scene: floor, walls, roof, small detail, medium
detail I, furniture, chairs, medium detail II, sills, boards and, finally, the rear storage and the windows in a single
texture set. After I'd finally discovered a proper UV packing addon for Blender, I computed my islands with it and got
a much more optimal result in contrast to my former projects, in which I used the default packer. Two angles with the
seams are shown below:

![Seam placement angle 1](/cdn/20230408/Classroom_9.png)
![Seam placement angle 2](/cdn/20230408/Classroom_10.png)

### 5. Texturing

With this project, I pushed Substance Painter's texturing and baking tools to their limits with the sheer scale of my
textures. To put it into perspective, I had 11 texture sets, each of which produces 7 4096x4096 textures in the
Substance editor, and 7 8192x8192 textures when rendering them out in Blender (so 77 8K textures in total). On top of
that, for each of these texture sets, I baked 5 4096x4096 maps (normals, world space normals, curvature, position and
thickness maps), so only the `.spp` file (any Substance Painter project's extension) weighed ~3.1 gigabytes on disk,
causing the program to lag heavily, crash ever so often unexpectedly on my high-end RTX 3090 Ti + Ryzen 7 + 32GB of
RAM system and simply saving my progress took about 20-30 seconds on a high-speed NVME drive, so texturing this scene
was, to put it lightly, frustratingly painful.

And when I mentioned earlier that this photorealism goal was mind-crushingly difficult to accomplish, I did not
exaggerate. When I was finalizing my textures, I'd already spent more than 40 hours of my life and was mentally exhausted
from the amount of stress induced by my responsibilities of not only completing my part, but also checking in and fully
coordinating and helping with the work of my partners, so at that point I was on the brink of quitting this unending
venture into architectural visualization, and my study results were dropping from the amount of time I was burning on
this project. And yet I forced myself to push onwards and finish everything up in the short amount of time that we still
had.

As for the texturing pipeline itself, it felt a little more stable since I didn't have to preserve stylization and instead
needed to use the more familiar photorealistic 4K/8K workflow. I sourced my materials from the default Substance Painter
collection, from Substance Community Assets (e.g. Substance Share) and some from outside sources like AmbientCG and other
websites, and spent hours upon hours tweaking the properties of materials and layers to preserve as much parity with the
room's photographs as I could, given my strict time constraints. Here are a few screenshots of the results, and keep in
mind that these previews from Substance Painter don't take any lighting or post-processing effects into account, so, in
reality, these textures look a lot more presentable:

![Angle 1 of the preview textures](/cdn/20230408/Classroom_11.jpg)
![Angle 2 of the preview textures](/cdn/20230408/Classroom_12.jpg)
![Angle 3 of the preview textures](/cdn/20230408/Classroom_13.jpg)

### 6. Rendering and Printing

After I'd exported the Substance project into 77 8K textures (of which around 20 weren't used in the final result out of a
lack of necessity or them introducing no meaningful data into the scene), I reimported them back into Blender with the
default Principled BSDF shader that losslessly ported everything over, and then contemplated the render settings. In the
end, I went with the following settings:

- `.tiff` format that would retain all the detail without any hint of compression and also works well with specialized
A1 printers
- A 12615x8910 pixel image that roughly corresponds to the √2:1 side ratio of A1 paper (with slight deviation around the
edges that, due to my miscalculation, caused small white bars on the paper)
- 16 bit color depth that corresponds to the depth of the textures and of the flat posters
- 2048 lighting samples (with the Cycles render engine), which turned out to even be somewhat unnecessary
- Default contrasting settings, since increased or decreased contrast would conflict and break the feel of the textures
and lighting

And after finalizing the camera angle and adding semi-realistic (though not exactly the same) lighting, I rendered the scene
out in ~55 minutes with my high-end graphics card. Here's a preview that I compressed down to a much lower resolution because
the full image takes up ~800-900 megabytes in a `.png` or `.tiff` format (with my partners' work blurred out):

![Compressed render preview](/cdn/20230408/Classroom_14.png)

After I'd printed the render to A1 paper, I also made an animation, in which the camera rotates around the entire room and
shows most of the detailing I'd done, but sharing it while respecting the privacy of my partners' work would be quite
troublesome. To summarize, this was by far my most ambitious, complicated and straining project since the beginning of my
3D journey, and I'm more than proud of the result.

## To Conclude

I'm highly unsatisfied that I wasn't able to meet even the seemingly light schedule announced in NL1.15, but, in order to
compensate for my prolonged absence, I've made sure to commit to the high quality standards of an article and have
described in exhaustive detail almost every project I've completed in these past few months (with exception of the one I'm
currently working on).

The newsletter is now nearing its 1 year anniversary on May 8th, and it feels great to look back on just how drastically
the quality of the pasts has increased since the very first post, NL0.1, and even since the last post after phasing out
the unordered list format. And, moving forward into 2023 and 2024, this newsletter will continue to adhere to the same
guiding principle that was set in stone from the beginning: quality over quantity, even if that means fewer releases and
longer breaks between them. The next post, NL2.16, will likely release in June, thereby marking the beginning of my summer
break.
