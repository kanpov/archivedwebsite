---
title: "0.8: Going Deeper into 3D"
date: 2022-06-26 +0300
excerpt: "Firstly, I re-did the lighthouse scene from the last post..."
---

### English

- This week, we haven't been actually working on a TED talk like usual: I've been working on writing my
 own article in a format that is alike to a TED talk's script
    - The topic for the article is language learning, and the title is (as of now, it is subject to 
    change): _The Happy Medium of Language Learning_
    - In the article, I address what I think is the reason why so many fail at learning a language and
     give some fairly universal advice that has worked for me
- Sometimes when I'm working on a TED talk I get inspiration from the topic and end up writing somewhat
 of an article instead of notes
    - So, I decided to try and separate that and actually polish and review the articles in order to
     publish them in the article section of this website, which is currently empty
    - This would solve the problem of me not having enough time to work on articles (as we're going to
     do one _or_ the other) and add some more content to the website
- On the actual lesson, I presented the early draft of the article (which took me a few days to write
 up) and received some valuable feedback
- Therefore, I still have quite a bit of work to do on it before I can actually publish it, as I don't
 think it has reached the quality standard I'm aiming for for these articles
- I hope I will've finished working on it by the end of next week, so look forward to an update in the
 next post!

### German

- On the first lesson, I worked on some more revision and test exercises and some exercises on the
 Preterite tense
	- I learned the Preterite on my own, so it was no problem
- On the second lesson, we started a new Unit about the Middle Ages period of history
    - Since I learned about it in 6th grade, I know a decent amount about that time period
    - To make it a bit easier for me, I learned some of the new words before the lesson
- I've started noticing major signs of improvement in my German speaking skills, which is really
 uplifting, as it's often frustrating to just persevere and keep learning
- Also, I won't have German lessons next week so this section won't be present

### 3D Graphics

- Firstly, I re-did the lighthouse scene from the last post, which was pretty successful:
![The rendered image of the redone lighthouse scene](/cdn/20220626/RedoneLighthouseRender.png)
- Afterwards, I moved onto a new project from the tutorial series: the well scene
    - The scene is not that fancy, but I learned some pretty useful modeling techniques from it:
        - Archimedian Curves from the _Extra Curves_ addon
        - Beveling curves
        - Extruding curve endpoints to extend them
        - Converting curves into meshes to apply further adjustments in Edit Mode (for example, beveling
         edges)
        - Using the _Decimate_ modifier to reduce polygon count so as to achieve a more low-poly-looking
         result
        - Using the _Clipping_ setting of the _Mirror_ modifier to mirror a half-part of an object to
         create the full shape
    - Here are the two images I got from the two passes (first pass is from following along with the
     tutorial, second one on my own):
![The first render of the well scene](/cdn/20220626/WellRender.png)
![The second render of the well scene](/cdn/20220626/RedoneWellRender.png)
- Lastly, I took on arguably the most complicated project I've done so far: the coffee shop
    - The scene has a lot of small details and I learned a lot from doing it
    - This was the most time-consuming project so far: the first pass took me 4 days and the second
     I crunched through in about 5-6 hours of non-interrupted work
    - New techniques learned:
        - Using loop cuts to control the bevel amount
        - Subdividing faces in Edit Mode
        - Individually insetting faces
        - Inverting selection
        - Using NURBS Path curves
        - Adding Text objects
        - Extruding Text objects
        - Using the _Spin_ tool to curve faces along a certain axis
    - Here are two renders:
![The first render of the coffee shop scene](/cdn/20220626/CoffeeShopRender.png)
![The second render of the coffee shop scene](/cdn/20220626/RedoneCoffeeShopRender.png)

### Competitive Programming

- In last week's post, I explained the direction I was taking with competitive programming and my
 motivation behind it
- To recap the progress of the prior few weeks, I completed
 [this course](https://stepik.org/course/363/info) on [Stepik](https://stepik.org), which taught
 the basics of the C++ language:
    - Basic arithmetic
    - Conditional statements and ternary operators
    - `while` loop
    - Floating-point arithmetic (`float`, `double`, `long double`)
    - `for` loop
    - Expandable arrays with `std::vector<T>`
    - Nested arrays or matrices
    - Functions and recursion
    - `std::string`s and `char`s
    - `std::map<K, V>` and `std::multimap<K, V>`
    - `std::set<T>` and `std::multiset<T>`
    - Built-in STL algorithms from the `<algorithm>` header
- In order to revise the basics and expand my knowledge, I've decided to take
 [a similar course](https://stepik.org/course/80538/info), which is specifically oriented for
 competitive programming
- I've been working on it the entire week and completed about 70% of it:
    - Variables
    - Loops and `if` statements
    - C-style arrays and matrices
    - Functions and recursion
    - Pointers (`int *i`) and references (`int &i`)
    - `struct`s: fields, methods, constructors and destructors
    - Operator overloading
    - `std::vector<T>` (currently working on)
- I also went through some of the older [VOS](https://vos.olimpiada.ru) exercises
 (here are the [exercises](https://vos.olimpiada.ru/upload/files/Arhive_tasks/2021-22/school/iikt/tasks-iikt-7-8-sch-msk-21-22.pdf) and the [answers](https://vos.olimpiada.ru/upload/files/Arhive_tasks/2021-22/school/iikt/sol-iikt-7-8-sch-msk-21-22.pdf) to them)

### Mathematics

- I haven't been working much on mathematics this week, though I did manage to get some stuff done
- I decided to go through some more intricate topics in the algebra textbook I've been using that
 were not present in the main curriculum:
    - Solving equations with monomials and polynomials
    - Solving text-based exercises by formulating a polynomial or applying the one that was given
- In terms of geometry, I worked further on the topic about polyhedrons and completed the much more
 frustrating topic about unwrapping and drawing polyhedrons by hand (which no sane person ever does)

### 1 Month Anniversary

- Lastly, I'd like to look back on the 1 month that has passed ever since I started learning 3D
 game development (and the associated fields)
    - This date is based on the 0.4 post, first mentioning the journey, which was released on
    the 30th of May after roughly a week of progress
    - So, the approximate beginning of my learning journey was sometime around the 24-26th of May,
    meaning that it has already been a month
- **3D graphics**:
    - Created the donut from the famous Blender introductory tutorial to learn the basics of the UI
    - Created the simple bedroom from 3DGreenhorn's beginner tutorial
    - Created 4 of the more complex and stylized rooms from 3DGreenhorn's course (3 entirely on my own):
        - The living room
        - The bedroom
        - The bathroom
        - The kitchen
    - Started following 3DGreenhorn's fast tutorial series to improve my skills and created:
        - A water tank
        - A light house
        - A well
        - A coffee shop
- **Programming**:
    - Started learning C++ with a basics course from [Stepik](https://stepik.org)
    - Continued learning with a more competitive-oriented course
    - Determined the direction in terms of competitive programming and started preparing
- **Mathematics**:
    - Went through about 75% of the 7th grade algebra curriculum
    - Started revising the fundamental concepts of geometry
