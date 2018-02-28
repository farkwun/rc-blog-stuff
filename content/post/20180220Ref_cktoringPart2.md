---
title: "More Ref*cktoring"
date: 2018-02-20T05:51:12Z
---

While I've certainly started arriving at RC at a reasonable time again, I definitely haven't stopped staying super late. 

I got in this morning just after 10 AM, and I am currently writing this blog post at 1:52 AM.

That's a winning combination.

### General Thoughts

I somehow found myself on the events committee for RC and I'm helping out with a lot of the events in the coming weeks.

Some of the events from my first half-batch really helped make me feel more at home and part of something bigger, so I suppose I'd better pay that feeling forward.

Of course, I'm definitely only using it as an excuse to make little progress.

That said, I did make a requisite tiny amount of progress today, which is probably the reason I'm still at RC so late in the first place. There was a particularly interesting concert at Times Square today - [INTERFERENCE A/V](http://arts.timessquarenyc.org/times-square-arts/projects/at-the-crossroads/interference-av/index.aspx) - a music concert held in a movie theatre with an additional twist: super cool combined visualizations. It was really interesting, even if the ushers wouldn't let us dance. It ended at 10 PM, which is probably when I should've gone home, but the party never stops.

Today was also the classic first-week pair-programming workshop for the new batchlings - the topic was [ref*cktoring](https://www.urbandictionary.com/define.php?term=refucktoring) again, mostly because it was so popular the last time and doing gross stuff to code never really gets old.

### What I did
I ref*cktored today with one of the new Spring 1 batch members, BL. He's the RCer that walked me through [Vagrant](https://www.vagrantup.com/) yesterday!

Our task was fairly simple - write a function that converts a string to binary and back. We decided to split them into two functions.

Here was our first-run at some fairly well-behaved functions:

```python
# take a string of 1s and 0s and converts it to a decimal numebr
def b2d(binary_string):
  total = 0
  exponent = 0
  for character in reversed(binary_string):
    total += (2 ** exponent * int(character))
    exponent += 1
  return total

def d2b(decimal):
  bstring = ""
  while decimal > 0:
    if decimal % 2 == 0:
      bstring += "0"
    else:
      bstring += "1"
      decimal >>= 1
   return bstring[::-1]
```

These gentle, innocent functions were converted into these:

```python
from operator import add

def a(f):
  return reduce(add, [c * e for (c, e) in zip([1 << g for g in range(len(f))],[ord(g) == 0x31 for g in f[::-1]])], 0)

def b(h):
  def d(h, i):
    return d(h >> 1, (i[::-1] + chr(48 + (h % 2 != 0)))[::-1]) if h else i
  return d(h, str())
```

It was really, really cool working with BL. His ideas for ref*cktoring included using True/False values returned from conditionals as 1s and 0s, bit shifts to create exponents, nested list comprehensions, and truly unnecessary recursion and string reversals.

Good luck trying to figure out how the code snippet above even works. We were helped a lot by following one simple tip - screw up all your variable names AFTER you've done all your other inefficiencies. It allows you to create some truly astounding pieces of dumb clever obscurity.

I actually feel like I learned a solid amount about Python, especially when it comes to the possibilities of list comprehensions.

BL also uses [Vim](https://en.wikipedia.org/wiki/Vim_(text_editor)), which I thought would make it easier for us to pair. Boy, was I wrong. BL uses [hardcore mode](http://www.vim.org/scripts/script.php?script_id=4715), a special configuration of Vim that removes all of the crutches that newcomers to Vim rely on. Turns out, I've got a lot of them. I'm still so reliant on the arrow keys! I am ashamed.

Afterwards, I hopped on a call with [Heap Analytics](https://heapanalytics.com/), the company that sponsored our community cluster! The conversation was incredibly informal, but they're interested in doing some interviewing with me in April. Let's see how that goes.

Of course, it wouldn't be a late RC night without some unique conversations. KT talked me through her project in [Kotlin](https://kotlinlang.org/) - she's working on an Android app that links into an Arduino to build altitude maps for [Dar es Salaam](https://en.wikipedia.org/wiki/Dar_es_Salaam), a city in Tanzania.

The most fascinating thing that came out of our conversation was the [Elvis operator](https://kotlinlang.org/docs/reference/null-safety.html), one of the ways in which Kotlin ensures null safety - in other words, avoiding undefined behaviour and crashes due to unintentional null variables. Apparently, this is one of Kotlin's big improvements on classic Java for Android programming.

Super interesting!

Finally, I did actually do some work on [open-splendor](https://github.com/farkwun/open-splendor). I added a loading spinner in preparation for the asynchronous calls I'm going to have to make to my currently theoretical API, and  I also installed [thunk](https://github.com/gaearon/redux-thunk). Pitiful progress, I know, but it's something!

### What I learned
* Intro to Kotlin
* Going deep on list comprehensions

### Interests/Stuff to work on
* Splendor in React!
* Code up Knapsack problem!
* CTF!
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Kubernetes!
* MongoDB!
