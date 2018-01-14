---
title: "Game Night and I Suck"
date: 2018-01-12T06:46:29Z
---
It's like 4 am in New York and I'm finally home and writing up this post for the day. Tonight was Game Night at RC! I guess I'll put all the board game stuff in this section since it's not really very programming or productivity related.

Technically this was the last day of the week, though I plan on going in tomorrow and on the weekend maybe as well. Gotta try not to burn out.

Board game night was really fun, even if I was super burnt out by the end of the day. I started out with a game of [Carcassone](https://boardgamegeek.com/boardgame/822/carcassonne), an every-man-for-himself territory map-building game with some really interesting emergent co-operative mechanics that arise out of self-interest. I got destroyed but managed to not come in last.

Afterwards we played some classic [Avalon](https://boardgamegeek.com/boardgame/128882/resistance-avalon), a social-bluffing game in the vein of [Mafia](https://en.wikipedia.org/wiki/Mafia_(party_game)) with some interesting twists. The highlight was when the spies got hit with a worst-case scenario (first two missions were, by chance, all Resistance members so the spies had no chance to exert any influence on the game), but through a brilliant series of conversational traps with almost no information, LS, the Assassin spy, figured out Merlin and won the game for her team.

Finally, we ended with [Splendor](https://boardgamegeek.com/boardgame/148228/splendor), a board-game that KN had been mentioning a couple of times as Game Night drew closer - it was surprisingly complex for such a simple core concept, and it was interesting listening to TY talk about perfect-information and min-maxing.

Also I had a ton of pizza.

### General Thoughts
I thought today was going to be more triumphant, as I managed to finally finish setting up the evolutionary model for developing the neural nets, but it was a pretty rough day - nothing went smoothly. I tried implementing an [abstract Model class](https://www.ibm.com/support/knowledgecenter/SSGH3R_11.1.0/com.ibm.xlcpp111.aix.doc/language_ref/cplr142.html) in C++ so I could make the Client a little more extensible, but I ran into a lot of compilation errors and problems with pointer typing. I ended up hacking together a working solution but there was a lot of wasted time coding parts that ultimately got scrapped. 

The worst part was that, while I got the neural net initialization, mutation, scoring, and generation code working, I hit a huge bottleneck. Even with 1000s of concurrent actors, the actual actors themselves are managing evolution within their internal states, so you don't actually end up getting any speed-up at all. I didn't realize it would be so bad until I started running it and didn't get any meaningful results even after an hour. I might have to re-visit my entire approach, which isn't great.

I'm also a bit unhappy because I feel like I didn't end up learning too much - I thought I would be able to do something clever with the abstract model class, but I wasn't willing to do a deep enough dive into it to get it working. Because of that, most of the progress was just in putting together the algorithm, and didn't feel very new. Plus, it didn't work - bleh.

### What I did
The majority of the day was kind of spent coding all by myself, which I felt a low-level anxiety about all day. I kept wanting to be social but whenever I got up to have a conversation I just found myself thinking about the code, so I never really felt comfortable. I suppose I should be proud I finished what I envisioned - sucks that it didn't work.

Aside from that, I had some cool conversations. Talked a little bit with DS about [OpenGL Shading Language](https://www.khronos.org/opengl/wiki/OpenGL_Shading_Language) and her application for region- and location-finding within a given map. I also talked about this with EB a little bit - it seems interesting but isn't really in my interests right now.

We also had the weekly feelings check-in in Babbage today (all the rooms in RC are named after a prominent figure in CS history - I think my favourite is Lovelace). Feelings check-in was good but also kind of intense - the focus is on being open and saying whatever you want or are stressing out about in safe space, and I think that can be a bit intimidating in a different kind of way. I'm glad it exists though. Obviously, at some point it devolved into a conversation about cryptocurrencies.

The major highlight of the day though was the mini-presentations. Each one was 5 minutes and that time limit was very strictly enforced. Here were the presentations:

* CM demonstrated her chrome extension - a bookmark categorizer and tagger
* TL performed procedurally generated music in the style of an input song using [Clojure](https://clojure.org/) for MIDI parsing and Markov chains for note prediction. The songs she chose were a piano piece and a GBC song - the model actually did a pretty good job of creating fairly acceptable music.
* JF introduced us to his project for creating a Prolog-style mobile IDE web-app for easy coding on a mobile device (typing is annoying, which makes coding annoying - how can we fix that?)
* NB did a stunningly ambitious live-coding session where he tried to train a neural network to classify cats and dogs AND integrate it into an iOS app all in five minutes. He failed spectacularly, but he actually got really close (one line off!). He was complaining that if he had just had 2 more seconds he would've had it ready to go, but I think it was so much better and relatable that it ended the way it did.
* RS did a surprisingly calming talk on cans of worms when it came to programming, and to remember that even though there are tons of ways to learn how to solve a problem, often it's better to take things one step at a time and not worry about having to 'eat all the worms'.
* AR did a fun and interesting talk about using CSS to create art using just div, shadow, before, and after. I know AR has an interest in [Explorable Explanations](explorabl.es) and this felt really in that vein. Notably, she was able to create the RC logo with time to spare!
* MLW and AM did a hilarious demonstration of a JavaScript game written entirely within an hour and using assets built from markers on a whiteboard (we were all wondering what that giant map on the whiteboard was for). The game is informally called "floating lazily down a river" and the code is here: https://github.com/lazerwalker/flatjam
* LR demoed his logical deduction solver written in [OCaml](https://ocaml.org/)
* AW did a super out of this world talk on a new programming language he built based on what he calls 'directed messaging'. He put together a demo using code-blocks that I don't super understand, so I've attached his project paragraph here:

```
At RC, I'd like to work on what I call "directional messaging". It's a different kind of OO programming where all objects have a location and instead of specifying the receiver of a message by reference, you specify a direction (e.g., up, down, left, or right) and the receivers are whatever objects happen to be there. I recently did a little experiment with this -- an implementation of Candy Crush -- and I think that it has the potential to make a lot of programming tasks (especially games) easier and more fun. I'm interested in developing this idea further so that it can be used as the basis for a new programming language for kids.

One thing I'm particularly interested in making work at RC is a "debug mode" that lets you visualize the messages being sent as the program executes.
```

Finally, we finally got our own computing cluster at RC, sponsored by [Heap](https://heapanalytics.com) - [fast.ai](http://www.fast.ai/), here we come!

I think I might table the neural net stuff for a little while, maybe take another look at that Ruby linter. I've also been slacking off on the study groups I'm a part of.

### What I learned
* A little bit about abstract classes?
* Some modest pie about evolutionary neural nets
* Some more OpenGL background

### Interests/Stuff to Work On
* Rubocop for Metasploit
* Machine-learning client for Parallel Actors - reinforcement learning?
* Problem Set 1 of the [MIT Algos course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/)
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Something in OCaml??
* SOMETHING FUNCTIONAL (programmatically and literally)
