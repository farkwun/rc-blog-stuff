---
title: "Failure Talks!"
date: 2018-02-06T07:02:36Z
---

It's starting to look like I've decided to make extremely late blog-writing a very, very bad habit, as I am currently coming at you live at 2:04 AM from the famous Recurse Center.

Well. For a given value of "live".

I also only had four or five hours of sleep last night! I'm getting positively loopy.

In other words, look forward to a blog post that's smack-dab in nonsense, instead of bordering it like usual.

### General Thoughts
Now, this may be the lack of sleep and extreme fatigue talking, but I don't actually remember much of the day. It all feels so far removed, like some wonderful dream.

However, if I marshal myself, certain images do bubble to mind.

Today was also a full-on [open-splendor](https://github.com/farkwun/open-splendor) day, and I couldn't be happier about it - I've been doing the simultaneously unrewarding and deeply satisfying work of refactoring the entire application.

I thought I had done the lion's share of refactoring on Monday, but it was only through that process that I realized that my underlying data model was causing a lot of issues that needed to be resolved sooner or later.

I went with sooner.

Objectively, I did a lot of different things today and got to touch a lot of fairly disparate domains - not to mention having hours of pretty fantastic conversations with Recursers.

I suppose that's why I'm still here at 2 AM.

### What I did
[Windmill Engineering](https://windmill.engineering/) invited me out this morning to tour their offices and get a look at their product demo. The company is working on what they call [live integration](https://windmill.engineering/faq/) for [Golang](https://golang.org/): a twist on the typical [continuous integration](https://en.wikipedia.org/wiki/Continuous_integration) development pattern.

Their key value proposition is that, through some clever uses of [go list](https://dave.cheney.net/2014/09/14/go-list-your-swiss-army-knife), Windmill is able to store a snapshot of your codebase on every file write and run only those tests that affect and are affected by changed files. In theory, this would allow developers to run tests in parallel with their code-writing, instead of only on a [pre-commit hook](https://git-scm.com/book/gr/v2/Customizing-Git-Git-Hooks) or something.

It was fun getting to talk through code with the CEO, and they were really nice to let me tour the place even though we wouldn't be moving forward with any job offers. They don't do visa sponsorship, and I'm not an American citizen!

Still, they were really friendly and their code was cool - go check them out! They also have a [Medium](https://medium.com/windmill-engineering) and a [twitter](https://twitter.com/windmill_eng).

Afterwards, it was right back to RC for some more of that open-splendor grind. I got to hang out with MR today - we walked to the library and I got me an official [New York City Library card](https://www.nypl.org/library-card)! It was a surprisingly easy process.

She also showed me some of the work she's doing - procedurally generating landscapes and topology maps in order to create fake, but astonishingly believable tourism guides for procedurally generated countries! MR's projects are all so incredibly interesting and curious - she likes to describe her work as "totally un-monetizable".

I also got to pair with the RC [CTF](https://ctftime.org/ctf-wtf/) team on level03 of the [Strip LiveCD CTF](http://www.janosgyerik.com/hacking-contest-on-a-live-cd/). 

Some background on the Stripe CTF - you're given a [LiveCD](https://en.wikipedia.org/wiki/Live_CD) with an operating system containing six user accounts. Your task is to gain access to each of these user accounts, starting from level00 to level06. Each user account introduces its own unique vulnerabilities, and the whole challenge is oddly reminiscent to me of early 2000s online puzzle games like [notpron](http://notpron.org/notpron/).

Each user account has their password in their home directory in a [dotfile](https://en.wikipedia.org/wiki/Dot-file) named .password, and the task is to find some way to read the contents of this file for each level.

level03 introduces a C [binary](https://en.wikipedia.org/wiki/Executable) that has some very odd behaviour - ostensibly, the binary takes an index between 0 and 3 and an input string. Based on this index, the binary passes the input string to a corresponding function pointer within a function pointer array.

Very odd. As well, in the binary is a deprecated function that allows the execution of arbitrary system commands. How curious.

Long story short, we figured out the memory address of the deprecated run function using [nm](https://en.wikipedia.org/wiki/Nm_(Unix)), used [gdb](https://www.gnu.org/software/gdb/) to determine the virtual memory address of the main function and the input buffer, used a negative index offset to traverse the stack and point to a the memory address of the deprecated function, and finally [cat](https://en.wikipedia.org/wiki/Cat_(Unix))-ed the level03 password!

It was really cool, even though I basically contributed nothing to the effort and just oohed and aahed.

We also had our first Failure Talk at RC, and some brave souls presented to the room about some of the biggest failures they've experienced.

I went in hoping to take notes and talk about each of the presentations, but the talks ended up being fairly heartfelt and it didn't feel quite right to do so.

That said, I was astonished at the ambition and creativity of the presenters, even when their projects ended in failure.

Some notable topics were:

* Having a failed startup
* Abandoning a Kickstarter-like artistic project
* Being part of, and ultimately going down with, a company they believed in
* Failing to maintain a project at a past company and having to watch all that work go down in flames

The talk ended with a discussion on failure, how we recontextualize it sometimes in an attempt to get something meaningful from it, and how it can be healthier to not try to take any meaning from it at all.

### What I learned

* Even in failure, Recursers are pretty incredible
* Intro to messing with stack memory and function pointers
* [go list](https://dave.cheney.net/2014/09/14/go-list-your-swiss-army-knife)

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
