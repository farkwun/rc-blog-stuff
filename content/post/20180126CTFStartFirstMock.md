---
title: "CTF!"
date: 2018-01-27T07:18:59Z
---
It just occurred to me that, seeing as Fridays aren't official RC days, I'm already a quarter way through my batch!

It feels like no time at all has gone by - specifically, I've hardly got anything done at all on my personal projects. It's a disaster! I feel like I should spend one of the weekend days just staying in my room and hacking away at stuff - RC is great but maybe too much stuff is going on.

### General Thoughts
Today was probably the worst [MIT Algos](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/) day. 

Only one person actually finished the problem set, and it was a pretty unproductive meeting. I spent the first bit of the morning trying to get everything done in time, but then got super distracted with [CTF](https://ctflearn.com/index.php)! 

As I was getting ready to write this, I was super sad because I felt like I didn't do anything all day - but I forgot about all the awesome information security stuff I did.

Also, today was the formal start of some mock interview and general interview prep sessions.

### What I did
So aside from trying to hack together some arcane [line-sweep algorithm](https://en.wikipedia.org/wiki/Sweep_line_algorithm) for the MIT problem set, the best part of the day was probably the [Capture The Flag](https://en.wikipedia.org/wiki/Capture_the_flag#Computer_security) computer security stuff we did. Honestly, I felt like most of the work was just deciphering what dumb thing the example code was doing - not very fun.

The CTF we worked on was [this really cool one](http://www.janosgyerik.com/hacking-contest-on-a-live-cd/) where you're provided a [Live CD](https://en.wikipedia.org/wiki/Live_CD) and tasked with hacking your way through six user accounts, each one a higher level of difficulty than the next.

If you're interested in trying it yourself, I won't spoil it for you, but in getting through the first three user accounts, I learned a little bit about...

1) Executable permissions
2) $PATH exploitation
3) Browser and filesystem exploits
4) Program memory exploits

This is for sure one of those things I could never have done on my own without RC. It was a huge struggle even thinking of the right approach - doing it in a big team full of smart, friendly people was hugely productive and useful.

Afterwards, there was a mock interview workshop where we split off and got to take turns being the interviewee - it was fun getting back into it.

LP also did an interesting breakdown on some common implementations of Python data structures, notably [lists](https://www.tutorialspoint.com/python/python_lists.htm) and [dictionaries](https://www.python-course.eu/dictionaries.php).

Notably, LP covered [Timsort](https://en.wikipedia.org/wiki/Timsort), a somewhat arrogantly named sorting algorithm thats currently implemented in the Python source code, as well as a little bit about how Python resolves [hash collisions](https://en.wikipedia.org/wiki/Hash_table#Collision_resolution) under the hood of its dictionaries.

Oddly, insertion into a list doesn't seem to be quite [amortized](https://en.wikipedia.org/wiki/Amortized_analysis) in the normal way - instead of doubling when full (which is the normal way), [CPython](https://en.wikipedia.org/wiki/CPython) does some weird slower-growing method of handling dynamic arrays (check out [the source here](https://github.com/python/cpython/blob/master/Objects/listobject.c), lines 50-58). I don't really understand how you get a constant time insert without doubling, but the tentative consensus was that it probably does converge to some approximation of linear time over a large enough series of append() calls.

### What I learned
* Some additional details about Python data structures
* Intro to CTFs and information security!
* Some dumb MIT garbage

### Interests/Stuff to work on
* More CTF for sure!
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
