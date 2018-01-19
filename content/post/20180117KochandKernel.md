---
title: "Koch Snowflakes and Kernel Crashes"
date: 2018-01-17T03:43:02Z
---

I got in today at like 11AM, soundly missing the daily morning mock interview prep session. I feel like this blog is going to be the sad and upsettingly boring chronicle of my inevitable drift into vagrancy.

I'll try to overcome my baser instincts, but what are the odds of that happening?

### General Thoughts
It was another day mostly dominated by courses, notably [fast.ai](http://www.fast.ai/) and the [MIT Algos course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/), but I don't actually feel as negatively about it as before. The conversation this time was pretty interesting and we ended up getting a fairly large amount of work done in a short amount of time.

I feel like I'm learning a lot *about MIT problem sets* though, and not actually that much about how to break down algorithm and interview questions in a productive and meaningful way. A lot of my issues with the pset were issues with the wording or general conception of the problems themselves. Notably, RS did a bunch of delightful meta-solving (because they asked *this* question, *THIS* question must mean X), which was funny but not entirely revelatory.

I think I'll stick with it for now. Don't love it though.

Also, I finally got around to looking at the actual rulebook of [Splendor](https://boardgamegeek.com/boardgame/148228/splendor) and we super played it wrong on Game Night! I blame NB. There's a bunch of subtleties that complicate my game logic - might just ignore them for now.

I want to get stuff done! The lack of progress on Splendor is giving me anxiety!

### What I did
They weren't kidding when they called it [fast.ai](http://www.fast.ai/). A number of us collaborated (well, I say collaborated - it was mostly just JK doing all the work) on picking apart Notebook 1 of the fast.ai course. In a really short time we were able to train a binary classifier for skyscrapers and houses on [Resnet34](https://arxiv.org/pdf/1512.03385.pdf) (a powerful pre-trained neural net for image classification), and the rest of the group quickly generalized it for use on the [Digit Recognizer Kaggle competition](https://www.kaggle.com/c/digit-recognizer)... which brings me to the kernel.

So it turns out that if you set the size parameter for the image transforms too high (Pytorch has a number of utilities that allow you to generate additional training data from your existing dataset using transformations like crop, rotate, zoom, etc., - of course, there needs to be some minimum allowable safe transformation size, which is where the size parameter comes in) the Linux kernel totally crashes. Cool.

We also spent a bunch of time working on the first half of the [second MIT problem set](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/MIT6_006F11_ps2.pdf), which was about recursively rendering [Koch snowflakes](https://en.wikipedia.org/wiki/Koch_snowflake).

The twist was, instead of analyzing different algorithms that might do the same thing, the problem set asks you to analyze the same algorithm implemented on different image processing setups.

The problem set proposed several different image-rendering architectures (hardware acceleration, software acceleration, [rasterisation](https://en.wikipedia.org/wiki/Rasterisation) on the CPU, etc.,) and had us analyze performance and time complexities of the algorithm given each setup. I think it was actually quite interesting, and served to bring the realm of algorithmic complexity analysis to a semi-real application. 

The most fascinating section of the problem set was at the very end - we were given an architecture with a time complexity dominated by the actual rendering of the image based on area, and not the computation of the edges of the Koch snowflake. RS made an elegant proof using triangle centroids to show that the area of the Koch snowflake is necessarily finite, and therefore rendering on this architecture is, by definition, constant time.

Fascinating - but fairly divorced from reality. The computation of the Koch snowflake, as set out by the problem set, is exponential, and it would have to be quite the terrible render function to be utterly dominated by the final area. As well, once the "tricks" got ironed out ("Ohhh, THAT's what they're talking about??"), the actual complexity analysis was trivial. Doesn't feel great.

I did a little bit more CSS - I feel pretty awful because I didn't actually manage to get any work done on my Splendor app. I'm starting to get really worried that I'm going to get nothing done for 12 whole weeks.

Well - I mean, I put a Hello World into a placeholder repo on my Github, but I'm not linking that until I've got something more meaningful to talk about.

### What I learned
* How to solve MIT problem sets?
* Splendor has some lame rules that are annoying
* Pytorch is really magic

### Interests/Stuff to work on
* SHOW UP FOR MORNING ALGORITHM PREP
* Splendor in React!
* Putting together a more bare-bones neural net for Pytorch - fast.ai won't be there forever
* Rubocop for Metasploit
* Machine-learning client for Parallel Actors - STANDBY
* Problem Sets for the [MIT Algos course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/) - I GUESS 
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Something in OCaml??
* SOMETHING FUNCTIONAL (programmatically and literally)
* Kubernetes!
* MongoDB!
