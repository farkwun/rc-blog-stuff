---
title: "Afternoon Tea"
date: 2018-03-07T07:54:21Z
---
3 AM again.

I don't know what I expected.

### General Thoughts
Today is a momentous occasion.

I have officially deployed [open-splendor](https://github.com/farkwun/open-splendor) on my personal droplet - it's still reaaaally awful though.

Seeing it all play out I'm pretty sad about the project. It's still mega gross-looking and it feels like a project a better dev could've put together in a couple of days, nevermind 8 full weeks at the Recurse Center.

So I'm pretty sad about that.

Also, the very first game I played I got super destroyed - the only reason I didn't actually lose was because my server crashed.

Classic Bryan.

### What I did
Post-lunch prep is going surprisingly well, though I don't know how qualified I am to actually talk about that, as I spent most of the day at Afternoon Tea, organized by MR.

There's a [mochi](https://en.wikipedia.org/wiki/Mochi) place near RC that sells them 3 for $1.25, so I brought 36 for just $15!

Afternoon tea wasn't even the tiniest bit coding related, but I had a lot of fun making sandwiches, drinking fancy teas, and generally pounding unreasonable amounts of food into my aggressively expanding body.

VRC ran post-lunch prep in my stead. Today's topic was [binary search](https://en.wikipedia.org/wiki/Binary_search_algorithm), and apparently there were some issues.

I chose two questions, as per usual:

1. https://leetcode.com/problems/search-insert-position/description/
2. https://leetcode.com/problems/find-peak-element/description/

Apparently, almost nobody solved the second problem, and the general feeling was that the difficulty was a sharp increase from the last couple of days. I think doing this exact question in the very first [Intro to Algorithms](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/) problem set might have biased me to its tractability.

I had a pretty good conversation with PC and LR about some tweaks we might want to make tomorrow, notably having a 15-minute even-more-optional prep session for the prep session (it sounds even dumber writing it all out) where we'll introduce the concepts a bit and maybe show off some code samples.

Ideally we find some way of handling this that provides valuable to everyone!

Afterwards, I paired with LD on shipping [open-splendor](https://github.com/farkwun/open-splendor). I finally implemented [webpack proxying](https://webpack.js.org/configuration/dev-server/#devserver-proxy), which allowed me to rip out all the [cross-origin resource sharing](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) stuff I had to add to my response headers. I also got to play with [ngrok](https://ngrok.com/) an awesome utility for exposing services running on a local port to the public web.

Once I made the necessary tweaks to open-splendor to get it working with webpack proxying, it was really simple getting it set up for real.

If you insist, you can check it out [here](https://splendor.bryan-chu.com/). It looks awful, and it barely works, and I actually think I hate it.

At the end of the night I had an interesting discussion with KDM and RH about [prefix tries](https://en.wikipedia.org/wiki/Trie), specifically how to use them for wildcard matching.

We came to a solution (basically turning a prefix trie into a prefix graph, with every node in one layer connected to every node in the next layer), but I'm not actually fully convinced it works.

### What I learned
* [Webpack proxying](https://webpack.js.org/configuration/dev-server/#devserver-proxy)
* [ngrok](https://ngrok.com/) exists
* I might have wasted 8 weeks?

### Interests/Stuff to work on
* Splendor in React!
* [Seven Languages in Seven Weeks](https://geneticmail.com/scott/library/text/seven-languages-in-seven-weeks_p1_0.pdf)
* [MIT OS course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/)
* Code up Knapsack problem!
* CTF!
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Kubernetes!
* MongoDB!
