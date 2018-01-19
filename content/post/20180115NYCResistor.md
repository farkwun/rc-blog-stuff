---
title: "React and NYC Resistor!"
date: 2018-01-15T05:45:14Z
---

As it was MLK Day in America, today was also not technically an RC day, so it's cool that I came in like an hour and a half late. That's what I'm telling myself anyways.

I mean, I guess there's no such thing as late when everything is self-directed. In that case, perfect.

I was really surprised at how few people were about. A bunch of alums were in the space, too. It really feels like things have settled down now that the Mini 1 batch (comprising ~15 people) are no longer frequenting the Centre. We'll see if that's true when RC starts up again in full swing tomorrow.

At the end of the night, I got to check out [NYC Resistor](https://www.nycresistor.com/), a hacker/maker collective in Brooklyn. The space is very, very cool - they have their own laser cutter, 3D printer, and wood-cutting bot. Every Monday and Thursday they open the space for visitors to bring personal projects they'd like to work on or get help with in the space. Becoming a member is invite-only, but everyone was warm and welcoming.

One of the makers was wearing a [PodBelt](http://www.podbelt.com/)! I want one.

### General Thoughts
I think my project idea is starting to come together in my head, though I'm worried it's not very cool. But who am I trying to impress?

It's starting to look like my coming week is going to be very course-based, what with working through React tutorials, walking through the new fast.ai Pytorch course, and trying to muster some work done in the MIT Algorithms problem sets.

For some reason I feel like coursework and tutorials don't really count as real coding, though I'm aware that's probably a bad way of looking at it. It's just frustrating not moving forward on any application in any meaningful way.

### What I did
I had a really productive conversation with AB about the React app I'm interested in putting together - a sort of open-source game server a la [Spyfall](spyfall.crabhat.com). I was having a really hard time visualizing how to approach semi-persistent game rooms until I started hashing it out with him. He made me realize that the idea of a 'room' at all was purely an abstraction - I could just store game state data in its own table and have the view handle everything with [AJAX requests](https://en.wikipedia.org/wiki/Ajax_(programming)) to some central server.

I also got to spend some time working with JK on my fast.ai environment within the community cluster - turns out [Conda](https://conda.io/docs/), the environment manager we were using, had some weird issues down the line. It was great working with JK, as I learned some spicy new Linux commands like [watch](http://www.linfo.org/watch.html), as well as a brief history of source, ./, and general bash execution. Turns out my conception of these commands was totally wrong, as I had never made the connection that source was specifically useful for getting environment variables and that ./ was only necessary when running scripts in the current directory (so as not to confuse scripts with dotfiles). So smart!

Of course, getting all the cluster stuff finished means I also got to spend time going through Lecture 1 of the fast.ai course. It's pretty interesting so far, particularly [how to tune learning rates for neural networks](https://arxiv.org/abs/1506.01186). It's much more fast-paced than the canonical [Andrew Ng Coursera course on Machine Learning](https://www.coursera.org/learn/machine-learning), as the very first code sample trains a neural net to identify dogs and cats with a 99% accuracy. I'm hoping to do a deeper dive on some of these Pytorch commands though, and I'm uncomfortable with how magical everything seems.

The overwhelming majority of my day, though, was spent going through [SurviveJS - React](https://survivejs.com/react/introduction/) a React book that seems to be much deeper than [my first React tutorial](https://reactjs.org/tutorial/tutorial.html). I'm starting to get a sense of how props are passed around and how components are meant to fit together. It's still largely academic though - I want to get some substantial work done on the app before the end of the week.

### What I learned
* Intro to React
* Actually using venv correctly for once
* Intro to Pytorch

### Interests/Stuff to work on
* Something in React! - NEXT WEEK
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
