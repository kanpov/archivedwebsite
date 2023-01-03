---
title: "1.14: Seven Preparation Weeks Recapped"
date: 2023-01-03 +0300
excerpt: "The following is a detailed breakdown of the six weeks of preparation that I’ve gone through since the release of NL1.13..."
---

## Preface

- So, as is nowadays tradition with this newsletter, my absence has lasted for longer than expected, but my "solution" to this is basically to solidify this
  1.5-month absence as the norm.
    - What I mean by that is the fact that these posts will now be released strictly on the holidays I have off my studies. These holidays happen approximately
      every 6 weeks, so the newsletter schedule is fixed to this timeframe.
    - The next holidays I have are going to be in mid-late February (specifically, from the 19th to the 26th of February inclusive), so NL1.15 is due to be
      released in that time interval.
- While this schedule is certainly not ideal for quantity, to say the least, I want to put enough time and effort into my newsletter in order to maintain
  a reliable standard, and, with the preparation efforts, school, learning German and competitive programming, it is nearly impossible to write the newsletter
  without a hefty time allocation, which I can only receive during scheduled holidays.
- On the summer holidays of 2023 I might consider a weekly or biweekly schedule, but until then, if no circumstances change radically, the six/seven-week
  delays between posts will be the norm.
- To conpensate this lack of writing (and, partially, to further develop my writing skills in German), I've begun a frequent [jrnl.sh](https://jrnl.sh),
  in which I make entries on a daily basis.
    - jrnl is a command-line tool that lets me write plain-text entries and appends them to a readable journal file with each entry containing the date, time,
      title and content (title being the entirety of the text up to a sentence ending).
    - What's great about jrnl is also the fact that it seamlessly supports complete AES-256 (CBC) encryption of the journal to protect your privacy, a feature
      I've taken full advantage of.
    - I would've liked to publicize the journal alongside the newsletter, but consciously decided not to, in order to keep it a safe spot to keep even my most
      controversial thoughts in, unlike the newsletter, which is a publicly recorded medium.
- The following is a detailed breakdown of the six weeks of preparation that I've gone through since the release of NL1.13 (keep in mind that the numeration
  will not reset, but rather continue onwards from where the last post stopped):

## Week IV

- The assignment for week IV was incredibly tough to complete, and, even accounting for the fact that I had holidays that week, I was barely able to submit
  my result on time after having worked on it for around 20 hours.
- The subject was a mid-poly scientist character with their environment, which I first modelled:
![The frontal perspective of the model](/cdn/20230103/W4I1.png)
![The side perspective of the model](/cdn/20230103/W4I2.png)
- Then rigged by modifying a human meta-rig to fit the character and converting it into a usable rig with the Rigify addon:
![The rig of the model](/cdn/20230103/W4I3.png)
- Then added materials, lit up and rendered the scene:
![The materials of the scene without lights](/cdn/20230103/W4I4.png)
![The final render of the scene](/cdn/20230103/W4R.png)

## Week V

- The assignment for week V was creating a geography classroom, which I first modeled: (the skeleton model was imported from the Internet)
![The modeled version of the scene](/cdn/20230103/W5I1.png)
- Then I added materials from the Substance 3D marketplace, I had to improvise because none of the materials that the author used were actually available for
  free, but I think I got it looking decent:
![The scene with .sbsar materials added in](/cdn/20230103/W5I2.png)
- After lighting up the scene and adding some finishing touches like the fog near the windows, I got this result:
![The final render of the scene](/cdn/20230103/W5R.png)

## Week VI

- The assignment for week VI was a small one, it consisted of creating a small-scale portal scene. The portal's wavy details were accomplished by subdividing
  a place and using the Displacement modifier with a wavy noise texture, so it's actually not complicated to recreate:
![The solid version of the scene](/cdn/20230103/W6I1.png)
- After adding a camera, materials and lighting the scene up with the classic warm-cold color combination, I got this result:
![The final render of the scene](/cdn/20230103/W6R.png)

## Week VII

- Week VII's assignment was yet another infuriating character modeling exercise, and this time I didn't have holidays, which was further complemented by a
  variety of mild headaches during the week, so I only managed to complete 50% of the assignment on week VII, and got back to it as soon as the winter holidays
  started.
- This time, I could skip the rigging, lighting and rendering part, and only needed to finish the modeling, which was still by far the most time-consuming
  assignment in this entire preparation journey.
![Perspective 1](/cdn/20230103/W7I1.png)
![Perspective 2](/cdn/20230103/W7I2.png)
![Perspective 3](/cdn/20230103/W7I3.png)
![Perspective 4](/cdn/20230103/W7I4.png)
![Perspective 5](/cdn/20230103/W7I5.png)

## Week VIII

- The assignment for week VIII was surprisingly quick and easy, just an extremely low poly (even origami-like) dinosaur scene:
![The solid version of the scene](/cdn/20230103/W8I1.png)
- Though, with an extremely simple lighting and material setup, the result ended up looking somewhat decent, mainly due to the simplicity of the scene:
![The final render of the scene](/cdn/20230103/W8R.png)
- As mentioned earlier, I went back to week VII's assignment to finish the remaining half of it, and only after that started working on the assignment for
  weeks IX-X.

## Weeks IX-X

- I received the assignment for weeks IX-X as a set of exercises due to be finished until (inclusively) January 6th, so I'm going to cover this set of
  exercises for two weeks in one heading.
- The first exercise was to model a simple amphora from reference, which didn't take too long:
![The modelled amphora](/cdn/20230103/W9I1.png)
- The second exercise was to UV-unwrap the amphora using a video series, which turned out to be a long and infuriating process, as I struggled to understand
  why the instructions in the video couldn't work.
- It took a lot of digging and reaching out to my representatives for help to get rid of the various artifacts that every single UV operation seemed to
  relentlessly produce. Here is the result demonstrated with a debug texture applied onto the object using the UV map:
![The UV preview](/cdn/20230103/W9I2.png)
- And here are a few examples of how a UV map **shouldn't** behave:
![Artifact 1](/cdn/20230103/W9I3.png)
![Artifact 2](/cdn/20230103/W9I4.png)
![Artifact 3](/cdn/20230103/W9I5.png)
![Artifact 4](/cdn/20230103/W9I6.png)
- The unwrapping process turned out to be truly painful, I just hope it'll get better as I get more experience in it.
- The third exercise was to go through a tutorial series on Substance Painter that teaches the basics of the program by texturing a guitar model. After I got
  familiar with the navigation and the UI of Substance Painter and completed the texturing process, I got this result:
![](/cdn/20230103/W10I1.png)
![](/cdn/20230103/W10I2.png)
![](/cdn/20230103/W10I3.png)
![](/cdn/20230103/W10I4.png)
![](/cdn/20230103/W10I5.png)
![](/cdn/20230103/W10I6.png)
![](/cdn/20230103/W10I7.png)
![](/cdn/20230103/W10I8.png)
- Even after completing the tutorial, I didn't feel very confident in the program, so I also followed along Adobe's official Substance Painter texturing
  workshop and got this result:
![](/cdn/20230103/W10I9.png)
![](/cdn/20230103/W10I10.png)
![](/cdn/20230103/W10I11.png)
