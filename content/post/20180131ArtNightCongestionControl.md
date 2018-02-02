---
title: "Art Night and Congestion Control"
date: 2018-01-31T05:18:24Z
---
I don't want to jinx it, but I think I might be able to make it to the end of the week without spending any money.

There was a presentation at the [Two Sigma](https://www.twosigma.com/) building today with free pizza - they also foolishly left out snacks like dried strawberries, banana chips and peanut M&Ms.

Tomorrow there's a Job Fair and "food and drinks will be served". Easy.

I'm probably supposed to be prioritizing making professional contacts - but why do that when I can instead pack my body with free calories?

### General Thoughts
Today was great!

I made it for morning algorithm prep which was only made slightly awkward by a misunderstanding I had that I could attend and do it all in Python - turns out it was specifically a [Golang](https://golang.org/) prep meeeting. Oops. They still let me do a question though.

We also really successfuly time-boxed the [MIT Algos](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/) meeting today - we only went 15 minutes over schedule. A partial victory, but a victory nonetheless.

Finally, I made some really solid progress on [open-splendor](https://github.com/farkwun/open-splendor). That's right, I'm finally linking the repo, despite its undeniable continuing status as a garbage fire.

I think I'm one or two solid work sessions away from diving into the back-end and starting to puzzle my way through [AJAX requests](https://en.wikipedia.org/wiki/Ajax_(programming)). I'm probably only excited because I haven't had to do it yet.

### What I did
The question I whiteboarded this morning was [finding the index of a given string in a sorted list of unique strings, where the sorted list has been interspersed with empty strings](https://www.geeksforgeeks.org/search-in-an-array-of-strings-where-non-empty-strings-are-sorted/).

I'm really glad I got to whiteboard again - I'm getting to shake off the rust and figure out my bad patterns. Notably, I found myself getting reallly nervous and not thinking things through, probably because of the awkwardness of the Golang/Python confusion. 

Keeping my composure despite awkwardness or social missteps is definitely something I need to work on - it's not the first time it's been a problem. The nervousness also caused me to write realllly messily, which was an additional problem.

We also went through hash-tables in the MIT algos course - I thought it was going to be really quick and easy but it turns out there was a lot of conflicting viewpoints. I thought it was interesting but ultimately nothing particularly novel - most of the misunderstandings seemed to stem from the problem sets themselves. Maybe that's just me being salty though.

Afterwards, I got a really solid chunk of time crunching through a number of features for Splendor. I'm definitely ignoring some of the finer rules of the game right now, and I'm still far from being feature complete, but it's honestly starting to look like it may well be on the horizon.

A big highlight of the day was getting to go to the [Papers We Love](http://paperswelove.org/) meetup at the Two Sigma building, and not just for the free pizza and snacks. The talk was on a paper released by Google in 2016 about a new scheme for [TCP congestion control](https://en.wikipedia.org/wiki/TCP_congestion_control). 

Specifically, the new congestion control scheme is called BBR, for bottleneck bandwidth and round-trip propagation time, after the two parameters it uses as inputs to its control loop (doesn't quite roll of the tongue, though). Take a look at the paper [here](https://cacm.acm.org/magazines/2017/2/212428-bbr-congestion-based-congestion-control/fulltext#F1), it's fascinating.

As much as the Advanced Networks course I took last year had its annoying sticking points, I think I really, really find networking protocols and communication algorithms interesting. I think there's a messy elegance to the way it approaches optimization in an unstructured and unreliable world.

I was really surprised to find that, for the most part, [TCP](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) congestion was still handled using [additive increase/multiplicative decrease](https://en.wikipedia.org/wiki/Additive_increase/multiplicative_decrease), with a hybrid version of [TCP-Reno](https://en.wikipedia.org/wiki/TCP_congestion_control#TCP_Tahoe_and_Reno) still being used in Windows.

It gave me a nostalgic rush to be looking at bandwidth bottlenecks and round-trip-time propagation delay. I wouldn't expect myself to still be interested in networks after all this time, but I do still find all the little schemes engineers have created to squeeze performance out of their cables both immediately relatable and delightfully imaginative.

The actual protocol is fairly simple, though it does presuppose some basic understanding of how TCP works and how congestion is typically handled. The core premise used by modern TCP congestion control systems like [CUBIC](https://en.wikipedia.org/wiki/CUBIC_TCP) is to measure congestion indirectly through packet loss. That is, when a network is fully congested, packets will start being thrown away - TCP is structured such that the sender is kept aware of which packets ultimately make it through. Looking at it from this perspective, the general approach seems reasonable - increase the number of packets I'm sending at every time-step until I start losing packets (additive increase), then decrease my packet size by some factor (multiplicative decrease) and continue. In this way, I will eventually converge to the optimal number of packets for my network conditions.

BBR leverages some interesting methods of probing the network to determine key parameters, which it then uses to tune its sender throughput to the existing network, earning its self-given title of a "congestion-based congestion control system".

Read more on it if you're interested!

I closed off the night by running back to RC for Art Night! Basically everyone just piles into the lunch room and draws, sews, sculpts, etc.,

CF was using a sewing machine to create a bag when I got there, and I accidentally trapped myself into spending an hour colouring in a fish scale by scale.

### What I learned
* Intro to BBR
* More whiteboarding gotchas
* I'm bad at colouring!

### Interests/Stuff to work on
* SHOW UP FOR MORNING ALGORITHM PREP
* More CTF for sure!
* Look into rope series and CRDTs
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
