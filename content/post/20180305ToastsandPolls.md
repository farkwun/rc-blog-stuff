---
title: "Toasts and Polls"
date: 2018-03-06T08:41:59Z
---
I had both the pleasure and pain of trying Malaysian iced tea today - delicious, but it's 3:40 AM and I'm somehow still awake.

There are sure to be a number of ways I'll end up describing my time at RC, but I don't imagine well-rested is going to be one of them.

### General Thoughts
Apparently, there are technical demos this week!

Last time, I wasn't even close to a finished product.

I'm still not close to a finished product, but I actually think I might be able to have it playable by Thursday!

The very first post-lunch prep was today as well - pretty exciting, and it went alright, but I think there was a lot to be desired in its execution.

Also, I found out that Golden Steamer, a deliciously cheap and filling bun shop near RC is closed, perhaps permanently. At first, the only emotions I had were sadness and regret, but then LW published the overwhelmingly large list of health code violations that shut the place down.

So, I suppose there are some mixed feelings.

Is it bad I'm still hoping they re-open?

### What I did
Today was super productive!

I resolved a number of outstanding issues with [open-splendor](https://github.com/farkwun/open-splendor), and the application itself is starting to get more and more streamlined.

Notably, I implemented a bunch of fixes for [polling](https://en.wikipedia.org/wiki/Polling_(computer_science)) issues I was having, and also implemented [toasts](https://developer.android.com/guide/topics/ui/notifiers/toasts.html). Now that I look at it, it seems like this is totally not an actual concept in web design and is purely an Android thing - oh well. I don't have time for renaming, right?

I also finished turn-checking, notably turning off polling if its your turn (as state only changes on moves) and turning off any potential onClick events.

That is to say, I only have to implement [POST](https://en.wikipedia.org/wiki/POST_(HTTP))ing moves to the server, checking for winners, and a couple of odd [Splendor](https://boardgamegeek.com/boardgame/148228/splendor) rules I've been intentionally putting off.

I'm nervous about saying so, but I actually think might be able to get it there by Thursday.

Of course, it will only be playable using the god-awful [Flask](http://flask.pocoo.org/) server I've been using, but small victories, alright?

Today was my first time running post-lunch prep, a more approachable and low-commitment daily interview prep session. I started with [first unique character in a string](https://leetcode.com/problems/first-unique-character-in-a-string/), which was way too easy for everyone.

I think the change I'm going to make is to put up an easy one and a harder one! This week I want to do a different topic each day - tomorrow is going to be [linked lists](https://en.wikipedia.org/wiki/Linked_list)!

Still, people seemed to have fun [code-golfing](https://en.wikipedia.org/wiki/Code_golf) some solutions and doing weird optimizations. PC managed to get a solution in that was slower than 98% of all other submissions, while still passing the test cases and without using any weird "sleep" operations.

Truly incredible.

I also spent about an hour wandering through [the middleware section of the Redux guide](https://redux.js.org/advanced/middleware) with JLC, and I think I've gained a much better understanding of what exactly middleware is doing and how it modifies the current [dispatch-action](https://redux.js.org/basics/actions) structure.

Let's hope I can keep up the momentum! Although, sleeping at 4 AM certainly is not helping...

### What I learned
* A bit more clarity on middleware internals

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
