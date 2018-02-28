---
title: "Langston's Ant"
date: 2018-02-26T07:33:53Z
---
I had to write like three blog posts today!

It feels like a huge waste of time to be doing that at RC.

### General Thoughts
Maybe it's just because I didn't feel like doing the work today, but I'm really starting to notice a scatter-brain-ness when it comes to my work at RC. I'm constantly getting distracted and letting myself get pulled away by this or that, and I think my productivity is taking a massive hit.

I'm going to do my best to actually set aside time to work on my own projects and not get distracted throughout that duration.

That said, I finally started just throwing stuff haphazardly at [open-splendor](https://github.com/farkwun/open-splendor) and seeing what sticks.

I need to be at peace with not making the perfect design decisions every time, especially if its keeping me from moving forward.

Near the end of the day I actually was able to get into a nice state of flow regarding open-splendor, and if I can just keep that up I think I could make a substantial amount of progress this week.

### What I did
I spent almost the entire first half of the day writing stupid blog posts that I had to catch up on. I think it's a cool thing to do, but it's hardly something I want to be devoting significant portions of RC time to. I'm going to make an effort to only ever write blog posts the day of, even if that makes the blog posts even worse than usual.

Anyways, the big thing I did today was help set up the meet-and-code, which some of you may remember from 6 weeks ago. The basic idea is to just have more pair-programming in general, but in the specific pairs get given some problem that they have some amount of time to finish - that problem then gets iterated on and extra constraints (like no functions more than three lines, or no if-statements, or no numbers, etc.,) get added and it all just gets harder and harder.

This time, instead of the [Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life), the space paired on an entirely new cellular automaton - [Langston's Ant](https://en.wikipedia.org/wiki/Langton%27s_ant). It's another really interesting system that has some fairly unique emergent behaviours that grow out of even simpler rules than the Game of Life.

Basically, Langston's Ant is initialized somewhere on an infinite grid made up of black and white squares.

1. If the square the ant is on is white, turn 90 degrees right, flip the color of the square, and move forward
2. If the square the ant is on is black, turn 90 degrees left, flip the color of the square, and move forward

It turns out Langston's Ant will always converge to a highway like structure, though apparently this hasn't been proven.

The pairing problem seems fairly interesting with some somewhat unique implementation details - that said, this time I was an organizer so I didn't get to pair off with anyone and get some good coding in. 

Instead, I spent the time floating around the space and getting a quick and dirty recap of [Android](https://www.android.com/) development from KT. Aside from learning about some really great [IntelliJ](https://www.jetbrains.com/idea/) utilities, I also got a quick refresher on [string resources](https://developer.android.com/guide/topics/resources/string-resource.html), strict typing in [Kotlin](https://kotlinlang.org/), and using [SharedPreferences](https://developer.android.com/training/data-storage/shared-preferences.html) to store key-value pairs for user data.

I also finally jumped head-first into [Flask](http://flask.pocoo.org/) - I worry that I'm going to end up writing a lot of Flask code while I mock out this server, but for now I'm just going to deal with it. If I find myself writing too much code, I'll start transitioning into [Golang](https://golang.org/), but I'm writing extremely brittle and disgusting [Python](https://www.python.org/) and I couldn't be happier.

After all, who cares how this mock server works right?

### What I learned
* [Langton's Ant!](https://en.wikipedia.org/wiki/Langton%27s_ant)
* Reintroduction to Android programming
* [Flask](http://flask.pocoo.org/), but dirty

### Interests/Stuff to work on

* Splendor in React!
* [MIT OS course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/)
* Code up Knapsack problem!
* CTF!
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Kubernetes!
* MongoDB!
