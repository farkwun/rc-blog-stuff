---
title: "Pairing in React"
date: 2018-03-01T07:08:05Z
---
I'm still riding the high, and extremely low amount of sleep, from yesterday.

It seems I am indeed still counting, as I broke all previous records by coming in at a disgraceful 2 PM.

### General Thoughts
As I sit here, I can't for the life of me think of anything particularly distinctive I did today, though I still feel pretty positive about it over all.

I think there were a number of socially-affirming interactions, especially in the latter half of the day, even though I was pretty much asleep for most of it.

Of course, I also got a feature completed for [open-splendor](https://github.com/farkwun/open-splendor), so there's always that.

### What I did
I spent the majority of the day working on open-splendor, implementing the join game functionality and setting up for the shared board.

Also, it looks like a ton of people are all working on [React](https://reactjs.org/) for the first time! I paired with PL to help her implement a single-player version of [SET](https://www.setgame.com/set)!

It's really cool to be able to have other people who are struggling with React for the very first time - just like me! It's a lot more fun to figure stuff out together.

Still, I really feel like I hardly got anything done. Let's just talk about the presentations that went on today, and see where that leaves us.

Today's presentations were:

* PABC presented a talk on his progress working on a [React](https://reactjs.org/), [Redux](https://redux.js.org/), and [Flask](http://flask.pocoo.org/) application. Except, he actually finished his project. Sounds familiar - only he actually finished his project! Why am I so slow??
* RH did a talk on [sorting networks](http://pages.ripco.net/~jgamble/nw.html), specifically retelling the story of our silly premature optimization from yesterday
* BL gave a quick presentation on what he'd been able to learn about [DNS](https://en.wikipedia.org/wiki/Domain_Name_System) over the last week
* KT gave a fascinating talk on the history of [GPS](https://en.wikipedia.org/wiki/Global_Positioning_System) and the [FusedLocationProvider](https://www.google.com/search?q=fused+location+provider&oq=fused+location+provider&aqs=chrome..69i57j0l5.3829j0j4&sourceid=chrome&ie=UTF-8) for Android. She's been working on a utility application that allows a user to compare the relative accuracies of each of the individual location providers within the FusedLocationProvider (GPS, Wi-fi, cell tower).
* PD introduced a project he's been working on that he calls "Personal Entropy", an app that tracks his location for each day, clusters each datapoint into the likely location each point corresponds to, and creates a number of really interesting metrics and visualizations about his days. Notably, he was able to determine that, really, there were only 18 "types" of day that he experienced, and he was also able to determine, on a given day, how like each of othe other date types that day was. Super interesting.
* MB gave a quick demo of his [recurrent neural network](https://en.wikipedia.org/wiki/Recurrent_neural_network) for creating [trail names](http://www.blueridgeoutdoors.com/magazine/november-2017/trail-names-the-best-of-2017/)
* NL, of premature optimization fame, gave a quick demo of his actual project (and not just all the dumb stuff we did yesterday micro-optimizing one tiny piece of it) that is built using [WebAssembly](http://webassembly.org/)
* MA showed off his cool custom programming language, [Datafun](https://github.com/rntz/datafun), a hybrid between [Datalog](https://en.wikipedia.org/wiki/Datalog) and [functional programming](https://en.wikipedia.org/wiki/Functional_programming) using [sets](https://en.wikipedia.org/wiki/Set_(mathematics)) as core base datatypes.
* DP detailed a bug she encountered working with the [CHIP-8](https://en.wikipedia.org/wiki/CHIP-8) emulator using [bitmasks](https://en.wikipedia.org/wiki/Mask_(computing))

I feel a little bit lost on the day. This is what happens when you come in 4 hours late.

CF pulled me aside briefly and gave me a pretty interesting way of determining the location of the [instruction pointer](https://en.wikipedia.org/wiki/Program_counter) for use in [buffer overflow attacks](https://en.wikipedia.org/wiki/Buffer_overflow) - [de Brujin sequences](https://en.wikipedia.org/wiki/De_Bruijn_sequence)!

Basically, the idea is to overflow the buffer with an extremely large de Brujin sequence, overwriting the instruction pointer. Once the program tries to return, it will retrive the new value from the old location of the instrution pointer and try to go to that location - since we've overwritten it to a location that is almost certainly not in memory, the program should crash. At this point, we can use a debugger like [gdb](https://www.gnu.org/software/gdb/) to determine what memory address the program tried to jump to - that memory address will correspond to a unique subsequence of our input de Brujin sequence, allowing us to pinpoint the exact byte offset needed to inject our own memory location - just replace that substring with our desired location.

He noted that, while this is a very effective way of exploiting buffer overflows, its way less satisfying than figuring it all out by hand.

### What I learned
* [de Brujin sequences](https://www.gnu.org/software/gdb/)
* Coming in late really sucks

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
