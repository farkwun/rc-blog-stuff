---
title: "Job Stuff"
date: 2018-01-26T04:49:51Z
---
Oh man, today was a carb-filled bonanza. A bunch of us went to [Donut Plant](http://doughnutplant.com/menu/) and tried 6 or 7 of their donuts. They were all really, really good.

I also found out that I may have forgotten to back up my resume before reformatting my computer. Classic Bryan. I had an old backup, but it was at least a year out of date!

As per usual, I'm putting together safeguards for this after the fact - starting with keeping my resume up on GitHub. I can't believe I hadn't been doing it before.

### General Thoughts
Despite donut times, today may have been genuinely my least productive day at RC.

I woke up incredibly late, and I can't think of anything I actually got done. 

There were two career-focussed seminars today - one for updating your RC Jobs profile, and another for resume tips, which brought my sadly lost resume into sharp focus.

Not a good context for being unproductive.

I also realized I still haven't put together an actual project! I really need to make some progress on this Splendor app.

### What I did
This morning I dove into making more utilities for the [fast.ai](http://www.fast.ai/) crew. Working off the [leaf classification Kaggle files](https://www.kaggle.com/c/leaf-classification), I hacked together a quick Python script to sort the given images into a format that works with our existing [Jupyter notebooks](http://jupyter.org/). It felt really nice to be working effectively on a small and immediately tractable problem.

I was pretty proud of myself, until I at the fast.ai meetup that a number of other people had also put together a nice sorted image dataset. What a waste of time! This is what happens when we don't have a nice shared folder on the community cluster to help coordinate our efforts.

Aside from that, there was an RC Jobs profile workshop where we set up our internal RC profiles to be sent to recruiters, if that was something we were interested in doing. It was a useful task - just not too heartening when looking at all the projects other Recursers have under their belts.

The resume workshop was nice, I suppose, but didn't tell me anything I didn't already know. Bleh.

There was one highlight to the day though - weekly Thurdsay presentations!

* MR presented her procedurally-generated terrain maps using [Simplex noise](https://en.wikipedia.org/wiki/Simplex_noise), and combining it with [ray casting](https://en.wikipedia.org/wiki/Ray_casting) and [midpoint displacement](https://en.wikipedia.org/wiki/Diamond-square_algorithm) to create rivers that realistically cut through the landscape.

* AB did a quick presentation on "Why [Rust](https://www.rust-lang.org/en-US/)", using some Python examples to illustrate the difference. Talking to him afterwards, it seems like Rust disallows more than a single write-enabled pointer to any object, thereby immediately eliminating a number of thread-safety and concurrency issues. I can see why he likes it.

* JC did a talk on [Knowledge Graph](https://en.wikipedia.org/wiki/Knowledge_Graph) - a knowledge base baked into the Google search algorithm, and its relation to the [Semantic Web](https://en.wikipedia.org/wiki/Semantic_Web), an idea postulated by [Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee) to make information-sharing between machines on the web standardized.

* LW did a mind-blowing demo of his implementation of 'perspectiveless arial imaging' - what if, instead of moving through a video file frame by frame, you did the same thing but fixed one of the axes such that each frame always looks to be from the same perspective? What if you changed that fixed plane over time? The best thing about it was that his implementation to derive each of these transformations was less than 30 lines long!

* DAD talked briefly about his struggles trying to test conversions of [Scheme](https://en.wikipedia.org/wiki/Scheme_(programming_language)) to [x86](https://en.wikipedia.org/wiki/X86).

* PC demoed his project, [dateknight](https://github.com/mrcoles/dateknight), a 'universal date-time string formatting reference'. His motivation was that all of these different languages have different methods and syntaxes for representing the same date-time information. This is annoying - so how can we fix that? The demo was very polished for having been done in the span of just two or three weeks.

* JK did a presentation on [the Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life), but taken to the absolute extreme. Using [Golly](https://en.wikipedia.org/wiki/Golly_(program)), a Game of Life simulation tool, JK showed off some of the most mind-boggling things people have done with the Game of Life - including simulating the Game of Life USING the Game of Life (because certain patterns can create certain deterministic outputs (specificall the [glider](https://en.wikipedia.org/wiki/Glider_(Conway%27s_Life)))its possible to simulate a [universal Turing machine](https://en.wikipedia.org/wiki/Universal_Turing_machine)). If it's possible to simulate a Turing machine, you can then use this to do any computation! It was super cool.

* VRC did a presentation way over my head about unions in C++, and also demoed his Concentration game in [React](https://reactjs.org/). I'm so jealous! I wish I had something demoable!

### What I learned
* I haven't accomplished anything!
* Time is running out!
* Panic!!!

### Interests/Stuff to work on
* Look into rope series and CRDTs
* SHOW UP FOR MORNING ALGORITHM PREP
* Splendor in React!
* Putting together a more bare-bones neural net for Pytorch
* Rubocop for Metasploit
* Machine-learning client for Parallel Actors - STANDBY
* Problem Sets for the [MIT Algos course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/)
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Something in OCaml??
* SOMETHING FUNCTIONAL (programmatically and literally)
* Kubernetes!
* MongoDB!
