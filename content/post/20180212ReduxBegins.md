---
title: "Redux and VICTORY"
date: 2018-02-12T08:22:09Z
---
The saga of gradually later and later wake-up times continues, as our titular hero awakens at 11:30 AM, a mere full hour before he was supposed to be at RC.

I feel like that Monday and Tuesday last week is really paying it forward in the screwing up my sleep schedule department, but at a certain point I gotta just start Present Me instead of Past Me's increasingly diminishing transgressions.

### General Thoughts
Today was somewhat hit or miss, as I got in super duper late and didn't spend as much time working as I would have liked.

I managed to get over my initial trepidation regarding [Redux](https://redux.js.org/docs/advanced/) though, and I actually made a ton of progress in that direction.

Still though, I have some pretty mixed feelings about the day.

IS WHAT I WOULD HAVE SAID

HAD I NOT FINALLY ACHIEVED THE IMPOSSIBLE

AND FINALLY SOLVED AM'S AWFUL, AWFUL SEQUENCE

ALL IS TRIUMPH

### What I did
Having pretty officially closed off on all the refactoring last week, I decided to bite the bullet and start flipping through Redux.

Even though this was arguably an inefficient way of approaching my project, I actually think it was really great going through it this way - I have a really strong intuition about the problems with vanilla [React](https://reactjs.org/) in general.

I also totally did not end up watching the [Getting Started with Redux](https://egghead.io/courses/getting-started-with-redux) video tutorials and instead worked my way two really excellent guides - [one on the main issue Redux solves](https://css-tricks.com/learning-react-redux/) and the other [cleverly named "counter-example" tutorial](https://daveceddia.com/how-does-redux-work/), in which the author starts with a React app and transfers it all to Redux.

I'm really starting to get what people mean when they say that Redux is initially complex (what with its specialized vocabulary of reducers, dispatchers, actions, and stores), but is quite simple once you get the hang of it. I'm honestly astounded that things get done at all in vanilla React, and I'm already starting to grok the promise of Redux. What's more, I've already managed to restore the initial render of my mock data using Redux, and I've already started writing out my reducers.

JC also turned me on to ["ducks"](https://github.com/erikras/ducks-modular-redux), a methodology of ordering one's Redux modules in a more formalized and self-contained manner - and you know me, I'm always a sucker for organizational systems.

There have been rumblings among my more-skilled peers about how I'm going to need to start looking into [Middleware](https://redux.js.org/docs/advanced/Middleware.html) if I want to have a way to handle [asynchronous](https://en.wikipedia.org/wiki/Asynchrony_(computer_programming)) requests - which means I'm still not done learning all the technologies I need to get this front-end working! I think this is going to be the last library - at least, I really hope so.

But this isn't why you're here.

You're here for the juicy stuff.

You're here for the sequence.

For those of you who don't quite remember, AM's infamous sequence goes like this:

> 1, 2, 2, 3, 2, 4, 2, 4, 3, 4, 2, 6, 2, 4, 4, 5, 2, 6, 2, 6...

It came to me in a dream. I woke up this morning with a single thought vibrating in my mind - look at the indices of the odd numbers. Look at the indices of the odd numbers!

It turns out it was not actually that useful of an idea. Still, writing out all the indices finally brought about a single scintillating insight, motivated by a comment by AB about the indices of the 2s in the sequence.

To clarify, the first number, '1', has an index of 1. That is, the sequence is not zero-indexed. It might also help to know that any number in the sequence can be derived by its index.

If you give up, check out the solution [here](https://oeis.org/A000005).

Finally - I AM FREE!

### What I learned
* Intro to Redux
* ALL THINGS ARE POSSIBLE

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
