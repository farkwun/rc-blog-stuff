---
title: "Refactor-palooza"
date: 2018-02-05T05:37:39Z
---
This week did not have the very best start as I got in an hour late.

That said, I'm currently writing this at 12:40 AM, in the Recurse Center, so it's probably bad decisions all-round.

### General Thoughts
Today marked another step backwards when it came to coursework - I pretty much showed up to the [fast.ai](http://www.fast.ai/) meeting having made no real progress. 

Normally I spend Monday mornings going over lecture video for that week, but I got completely distracted by [open-splendor](https://github.com/farkwun/open-splendor).

In fact, I just got distracted doing more refactoring while writing this blog post - it's now 1:15 AM and I'm only on General Thoughts!

### What I did
On the recommendation of one of my good friends, I decided to block off my morning to improve my JavaScript environment. I've been using the [Syntastic plugin](https://github.com/vim-syntastic/syntastic) for all of my [linting](https://en.wikipedia.org/wiki/Lint_(software)), which is a roundabout way of saying I didn't do any linting because Syntastic is garbage and takes 1+ seconds to run, while also totally screwing up my [screen](https://en.wikipedia.org/wiki/GNU_Screen) sessions.

I hadn't even considered that there might be other options, as [CentOS](https://www.centos.org/) (my previous [Linux distribution](https://en.wikipedia.org/wiki/Linux_distribution)), forced me to use a pretty old version of [Vim](https://en.wikipedia.org/wiki/Vim_(text_editor)) - now I'm on version 8, baby!

Because of that, I was able to set up [ALE](https://github.com/w0rp/ale), or Asynchronous Lint Engine, as my linting plugin, and it runs like a dream. I also embedded [Prettier](https://github.com/prettier/prettier) into my ALE configuration so it would auto-format my code on document save.

My code is so beautiful now! It feels like cheating.

Also, despite my complete lack of effort in preparing for the fast.ai meeting this week, it still ended up being a pretty good meeting. LD and JM put together a Shakespearean text generator using one of the Henry IVs as input.

Even though the text generation wasn't that great, I still thought it was pretty cool. It looks like multiple groups are getting really into the [NLP](https://en.wikipedia.org/wiki/Natural-language_processing)-side of [deep learning](https://en.wikipedia.org/wiki/Deep_learning), as KS and AM are working on generating text using meditation manuals crossed with business management textbooks. 

I love it.

I spent the rest of the day going over my utility functions and my absolutely disgusting buyCard() function in open-splendor, and I actually found it extremely fulfilling. I thought I mind find it more annoying to have to refactor code, but it was so satisfying getting to put the theory I spent hours talking through with JC into practice.

A couple of the messier code chunks still stuck me though, so I also ended up getting [port forwarding](https://en.wikipedia.org/wiki/Port_forwarding) working on my [NGINX](https://www.nginx.com/) config, and put a working [Golang](https://golang.org/) site up on my server.

Later in the evening, I got completely side-tracked by a sequence AM put on the main whiteboard without any additional information. The sequence goes...

```
1, 2, 2, 3, 2, 4, 2, 4, 3, 4, 2, 6, 2, 4, 4, 5, 2, 6, 2, 6...
```

A big group of us must have wasted at least an hour and a half wracking our brains trying to figure out the rule. Of course, by the time we even noticed the sequence AM had already left the space for hours, and we were left with absolutely no hints at all as to the meaning of the numbers.

Just to make sure we weren't completely wasting our time, we plugged the sequence into the [On-line Encyclopedia of Integer Sequences](https://oeis.org/), and we verified that it was indeed a known sequence. To make things worse, RS and PJ both took a look at the entry and confirmed that it was not only a real sequence, but that it was possible for us to solve.

PC didn't help matters when he added his own sequence:

```
1, 2, 3, 2, 2, 2, 3, 3, 2, 2
```

I spent thirty minutes trying to crack it before caving and asking for hints. 

Try to figure it out! AM's sequence is still entirely undefeated though. I'll update you if any of us figure it out or if I cave, whichever comes first (in other words, when I cave).

If you want to know the rule for PC's sequence, check it out [here](https://oeis.org/A037195). In his defense, I don't think he knew it was an existing sequence, and neither did I until I looked it up just now.

Finally, even though it must've already been 10:30 PM, I pulled JC aside for a quick code review of the work I'd done so far on open-splendor. As is typical with our talks, we got completely sidetracked with interesting tidbits about JavaScript, React, and functional programming.

I feel like I finally have a good intuition for a use-case for [partial application](https://en.wikipedia.org/wiki/Partial_application), though [currying](https://en.wikipedia.org/wiki/Currying) is still a bit beyond me. He also thinks it's time for me to start moving my state into [Redux](https://redux.js.org/)! Should be exciting. He also introduced me to [Jest](https://facebook.github.io/jest/), though I pretty much only know that it exists.

The absolute biggest mind-blow though was learning about [JavaScript's tree shaking](https://webpack.js.org/guides/tree-shaking/)!!! It turns out that, unlike Python, importing specific functions from another file isn't just for [syntactic sugar](https://en.wikipedia.org/wiki/Syntactic_sugar) - it actually has a performance impact! JavaScript will **only include code that's required for the functions you've imported**, which is a sharp contrast to [Python's behaviour](https://stackoverflow.com/questions/9439480/from-import-vs-import).

This completely blows my mind - JavaScript is awesome in its power and functionality, and it honestly doesn't even look half bad now that [everything is all Pretty](https://prettier.io/).

I still have no idea about that sequence though.

IT'S 2:10 AM - I AM LEAVING THIS BUILDING!

### What I learned
* JavaScript tree shaking!
* Use-cases for partial application
* Intro to Asynchronous Lint Engine
* Intro to Golang servers
* Jest exists

### Interests/Stuff to work on
* Splendor in React!
* Morning Golang prep!
* Even more CTF!
* Look into rope series and CRDTs
* Problem Sets for the [MIT Algos course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/)
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Something in OCaml??
* SOMETHING FUNCTIONAL (programmatically and literally)
* Kubernetes!
* MongoDB!
