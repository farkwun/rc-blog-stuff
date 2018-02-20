---
title: "C o d i n g B e e"
date: 2018-02-07T05:55:26Z
---
Those late nights really caught up to me today -  I slept in on purpose and still woke up a mess.

Staying at RC late is fun, especially when I'm doing good work, but it's definitely not worth having super unproductive days afterwards.

### General Thoughts
I did a ton of fun stuff today, but it was all filtered through this grimy patina of sleep deprivation. I found it really hard to to focus on anything substantial for most of the day, and caught myself idling more often than I would've liked.

KT started working on an [Arduino](https://www.arduino.cc/) project using an [Adafruit barometric pressure and altitude sensor](https://www.adafruit.com/product/2651) to create better altitude maps for [Dar es Salaam](https://en.wikipedia.org/wiki/Dar_es_Salaam) in Tanzania. Apparently, flooding is fairly common there, and the drainage system doesn't have enough data to accurately predict which areas are most susceptible to flooding and why. However, in the process of doing so, she got really annoyed at the state of the RC hardware organization system and I found myself just helping her clean stuff up more than once when I totally had stuff to do.

Sleep deprivation is no good for my brain.

### What I did
Today was another [MIT day](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/), but it was one of my worst - unlike the [fast.ai](http://www.fast.ai/) course, I haven't been following the lecture slides or the course videos at all; I've mostly been just flying it by the seat of my pants.

That's typically fine, but it ended up not working out super great this time - the first question on the problem set required us to augment the [Bellman-Ford algorithm](https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm) to find what amounted to a shortest path among nodes in a graph - however, because I haven't been following the lecture sets, my implementation was just a straight-up [breadth-first-search](https://en.wikipedia.org/wiki/Breadth-first_search). Very inefficient.

RS figured out a surprisingly elegant augmentation for the problem constraints, which you can read about [here](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/MIT6_006F11_ps6.pdf).

Implementing my solutions was fun, even if they didn't end up being useful.

I guess the day was extra bad for sleep deprivation, because I'm in the final stretch of my refactor of [open-splendor](https://github.com/farkwun/open-splendor) and its getting fairly complicated.

Unlike my other refactors, where components failed loudly and messily, JavaScript's flexibility is allowing my changes to fail silently, or in places far downstream from its actual progenitor. I'm fundamentally changing a fairly integral part of my data model too, so it's a bit more of a slog than it otherwise be.

I decided to leave as soon as I caught myself writing shortcuts just to get one specific feature to work - that's how I got into this mess in the first place!

The big highlight of the day, though, was the RC Coding Bee!

Here's the RC blurb about it on the calendar:

> A Coding Bee is sort of like a spelling bee, but with code. Teams take turns spelling a small program out loud, one character at a time, without looking at it, in front of an audience. It's silly, fun, and a lot harder than it sounds.

Some additional rules:

* **EVERY** character, including tabs and newlines, must be spoken
* Aside from characters, a team member has two additional moves - "delete whole line" and "delete all" - nothing else
* 5-minute time limit!!
* Pass the tests to win points
* The points don't matter

My two-person team was with LW under the team name "The Wanna-Bees". Yeah. It was good stuff.

The Coding Bee was super, super fun, and it was really entertaining watching the moments of insight, inspiration, or straight up miscommunication among teammates. Our team went up a little late, so we got to figure out some cool meta-methods of transmitting information using clear-lines or conventions other teams introduced in their attempts.

It was especially interesting doing it in Python - at first, it seems a lot easier to write small programs with the expressiveness the language gives you, but keeping track of tab characters is a real pain. Maybe keeping track of curly braces is even worse though.

The whole one character at a time aspect reminded me a lot of [Codenames](https://boardgamegeek.com/boardgame/178900/codenames), in that you only have this extremely limited set of expressions available to you in order to communicate with your team.

The most interesting and challenging aspect of the contest was figuring out the approach your teammate has to the problem you've been given - sometimes they'll make choices that seem completely out of the blue, and its up to you to either flex your solution around theirs, or throw the entire line away.

I thought it would be more mind-wracking or embarassing pair-coding in this way in front of a live audience than it was, but also the RC community is mega supportive and encouraging so your mileage may vary.

### What I learned
* Review of [Bellman-Ford](https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm)
* Coding Bee meta-strategy
* Sleep is good

### Interests/Stuff to work on
* Splendor in React!
* Morning Golang prep!
* Even more CTF!
* Problem Sets for the [MIT Algos course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/)
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Something in OCaml??
* SOMETHING FUNCTIONAL (programmatically and literally)
* Kubernetes!
* MongoDB!
