---
title: "Non-Technical Talks!"
date: 2018-01-22T04:08:23Z
---
Today marks the first real day of my slow spiral into drug dependency.

I've been trying to get by at RC without caffeine, but I finally caved today and took a caffeine pill.

It was a super productive day.

Can't argue with those results, can ya, worried friends and family?

### General Thoughts
Today was great! I got a lot done and we had the first ever (as far as I know) set of non-technical talks in the evening. More on that below.

I don't want to blame it solely on the caffeine, but oh man did it help.

As is probably not a surprise to anyone, I also totally slept through morning interview prep. I'll get 'em next time.

### What I did
I cleaned up my [KeePass](https://keepass.info/) database and set up [syncthing](https://syncthing.net) on some of my new devices. I'm starting to really try to migrate everything off of my bug-ridden constantly crashing Lenovo machine, and I finally finished up a big step. Hello, [Antergos!](https://antergos.com/)

We had one of our twice-weekly meetups for the [fast.ai](http://www.fast.ai/) study group. A number of us feel like we have a good handle on [digit recognition](https://www.kaggle.com/c/digit-recognizer) and we formalized a push towards our next [Kaggle](https://www.kaggle.com/) competition - [leaf classification](https://www.kaggle.com/c/leaf-classification). One of the personal goals I've had that I haven't really been vocalizing is to try pairing with people a bit more, and I specifically wanted to work on some team utilities to make Kaggle submission easier.

Basically, despite having pretty much implemented a working multi-classifier using [Pytorch](http://pytorch.org/) and the [fast.ai libraries](https://github.com/fastai/fastai), we still hadn't actually submitted our predictions to Kaggle - mostly because none of us could figure out how to actually use our models on test data and convert it into a comprehensible format. I really wanted to work on some scripts or at least example docs that could streamline that process.

I ended up pairing with JM on a tight script to run the test data with our models and compress it into a comprehensible format for Kaggle. It was really fun and oddly productive diving deep in the fast.ai libraries and hacking stuff together - the cherry on the sundae was when we realized all the work we did was unnecessary and the answer had been staring us in the face all along.

I actually feel like I've come away with a pretty solid understanding of the fast.ai libraries though, so I'm not too beat up about it.

I also put together a big chunk of the outstanding components for Splendor! I think I'll be ready to start standing up a back-end soon - the front-end logic still escapes me though. I'm just going to try to get the basics working first - complex logic comes later.

Finally, I got to see non-technical talks by RCers! I suppose people wanted to talk about and share stuff that wasn't directly related to coding (though it could still be technical, just not CS). A lot of the presentations were really cool and really weird.

* AR talked about [lexical gaps](https://en.wikipedia.org/wiki/Accidental_gap) in the English language, specifically [morphological gaps](https://en.wikipedia.org/wiki/Accidental_gap#Morphological_gaps) and [semantic gaps](https://en.wikipedia.org/wiki/Accidental_gap#Semantic_gaps). She had some great examples of weird English rules and missing pieces that one might think would exist, but don't.

* RS did another esoteric talk about memorization techniques - he showed us his memorization of the [Chinese zodiac](https://en.wikipedia.org/wiki/Chinese_zodiac) using a technique similar to a [memory palace](https://en.wikipedia.org/wiki/Method_of_loci). He told the group this odd, violent, graphic story using each of the twelve animals in their proper order.

* HY did a brief introspective on cooking, specifically about her kitchen and its [mise en place](https://en.wikipedia.org/wiki/Mise_en_place).

* AK gave us a surprisingly personal look at the artwork she's been working on throughout the past year - a exhibit of race, blood, and technology. She started off by talking about her own issues with identity and racism as a mixed-race individual, and segued into her collection - blood batteries! By using blood, gelatin, metal and LEDs, she asked a question - if this circuit is powered by pure-race blood, does that make the machine more racially pure than she is?

* CW did a super meta talk on [Pale Fire](https://en.wikipedia.org/wiki/Pale_Fire), by [Vladimir Nabokov](https://en.wikipedia.org/wiki/Vladimir_Nabokov). It was a fascinating discussion on meta-fiction and meta-narrative, and CW ended it off with a perfect self-referential uncertainty.

* AM did a talk on [rods and cones](https://www.cis.rit.edu/people/faculty/montag/vandplite/pages/chap_9/ch9p1.html), and how our displays leverage this property to simulate colour to the eye.

* LW gave a super interesting talk on why New York water tastes so good (I didn't realize until he mentioned it, but it totally does taste really good). It turns out that NYC's water [is totally unfiltered](http://blogs.ei.columbia.edu/2011/07/29/maintaining-the-superiority-of-nyc%E2%80%99s-drinking-water/). What's fascinating is how that arrangement came to be legal - NYC's water is allowed to be unfiltered as long as it maintains the environment of the [Catskills](https://en.wikipedia.org/wiki/Catskill_Mountains), where it gets its water! As long as NYC keeps the environment pristine, it doesn't have to filter its water.

* PM gave an interesting talk on [Clairnote SN](http://clairnote.org/clairnote-clairnote-sn/), a new standard for musical notation aiming to be more clear and less arcane. He even tied it back to [the first half of the Zen of Python](https://www.python.org/dev/peps/pep-0020/), which I think it's worth putting here:

```
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
```

The non-technical talks were great, we're going to be doing another chunk of them sometime in the coming weeks so keep your eyes peeled for those!

### What I learned
* NYCs water is delicious and why
* Standard musical notation is garbage
* Some of the weird arcanity of the fast.ai library - you can totally tell it was written by grad students ("single letter variables are easier to type, okay?")

### Interests/Stuff to work on
* SHOW UP FOR MORNING ALGORITHM PREP
* Splendor in React!
* Putting together a more bare-bones neural net for Pytorch - fast.ai won't be there forever
* Rubocop for Metasploit
* Machine-learning client for Parallel Actors - STANDBY
* Problem Sets for the [MIT Algos course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/) - still with it so far
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Something in OCaml??
* SOMETHING FUNCTIONAL (programmatically and literally)
* Kubernetes!
* MongoDB!
