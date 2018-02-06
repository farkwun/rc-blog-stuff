---
title: "Sharif CTF"
date: 2018-02-02T00:31:23Z
---
I haven't quite decided on whether I want this section to be at least somewhat related to the rest of the blog post or if it's instead meant to be for personal updates and blog meta-reflections. Or blog meta-meta-reflections.

I definitely know which option we've been going with so far.

### General Thoughts
[Mapbox](https://www.mapbox.com/) came in to do a big hack-and-tell day - Mapbox engineers came in to introduce RCers to their platform and act as mentors and sources of information for anyone who wanted to do some hacking with their APIs or on related projects.

I was initially pretty excited about attending, but I got totally side-swiped by [Sharif University's 2018 Capture the Flag Competition](https://ctftime.org/event/507). First place winner gets 35 000 000 Iranian rials! I ended up spending the entire day working on it. It was supposed to be a full 36 hours, but we got the time wrong - the contest started at **1:30 AM**, not PM!

I've been feeling really great about RC this week, and today was no exception - working on an actual CTF with the RC team was way more fun than I thought it would be, and I'm really glad I was able to actually contribute this time around.

### What I did
So, unlike [last week](http://www.janosgyerik.com/hacking-contest-on-a-live-cd/), the Sharif University [CTF](https://ctftime.org/ctf-wtf/) was really cool and approachable, using [Jeopardy](https://en.wikipedia.org/wiki/Jeopardy!)-style categories like Web, Crypto, and Misc.

The very first Web CTF, for example, was worth 50 points and involved just finding a sentence on the rules page and finding its [MD5 hash](https://en.wikipedia.org/wiki/MD5). Each challenge involved calculating or uncovering a specifically formatted "flag" (just a text string) within the provided challenge context and submitting it to the site.

I paired with CW on a CTF involving a list of 128 [15 puzzles](https://en.wikipedia.org/wiki/15_puzzle), each one representing a one if solvable and a zero if not. Once we had our string of 128 1s and 0s, we hashed it to uncover the flag! It was probably one of my first really collaborative pairing sessions since I've joined RC.

Some of the other challenges that the team tackled were:
* Restoring a corrupted PNG with the flag - SOLVED
* Finding a flag within the source files of an [APK](https://en.wikipedia.org/wiki/Android_application_package) - SOLVED
* Trying to crack an encrypted docx
* Bruteforcing a webpage login implementing a terrible form of [CAPTCHA](https://en.wikipedia.org/wiki/CAPTCHA)

It was the last one I spent the majority of my time doing - and probably the one that the majority of the other teams spent their time doing as well, considering how often the site went down while I was testing my POST requests.

Actually, that was the biggest problem with the CTF - the site went down really early on, so we could only work on the challenges we had happened to pull down onto our local devices. I guess that's what happens when one of your challenges requires flooding another site on the same server with login requests.

We only really ran out of steam when we got stuck trying to get [OpenCL](https://en.wikipedia.org/wiki/OpenCL) working on our community cluster to try bruteforcing the encrypted docx password with [hashat](https://hashcat.net/hashcat/). Maybe it was the wrong approach regardless.

Once the site went down, we all broke for a little while to do our regular Friday interview prep. It was pretty fun, and I also got to ask someone one of [my favourite questions in recent memory](https://www.geeksforgeeks.org/median-of-stream-of-integers-running-integers/).

### What I learned
* [The surprisingly involved proof for solvability of a 15-puzzle](https://www.geeksforgeeks.org/check-instance-15-puzzle-solvable/)
* Intro to hashcat
* Intro to Iranian currency

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
