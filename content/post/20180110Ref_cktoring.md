---
title: "Pair Programming and Ref@cktoring"
date: 2018-01-11T03:17:15Z
---
I caught myself somewhat stressing out about these daily blog posts on the train home today, and also kind of thinking about interactions through the lens of having stuff to talk about here. 

That's super not what I wanted to accomplish by writing this and I don't think it's worth having it take up too much mental space. I definitely shouldn't be worrying about it. I think I'm going to handle it by not caring at all and producing bad content. 

### General Thoughts
Today wasn't really as productive as I wanted, or maybe just not in the right ways. I managed to put together some of the basic neural net code for [Parallel Actors](https://github.com/farkwun/ParallelActors) but I still didn't get much of the evolution part working. Also, I had a conversation with NB near the end of the day which made me re-think some aspects of my approach. 

I definitely still want to get the evolutionary neural nets working, probably because it feels just within reach and would be enjoyable to put together, even if not particularly challenging.





### What I did
I had some good conversations today, notably over lunch about functional programming and how they fit in as a tool to create applications. I had a great talk with LR about his project (a logic statement prover - he calls it a 'logic homework grader', written in [OCaml](https://ocaml.org/). AB was also there (he's working on a Lisp intepreter using Rust) and I think I gained a bit more insight on what functional programming is about. I had heard already that it helped prevent side-effects, but I hadn't really gotten a satisfying answer on the particular applications for which functional programming languages are well-suited. On reflection, I still feel like I don't have a great sense, but I think the idea of 'everything immutable' is pretty interesting.

VRC came over and started talking about the [MIT Open Courseware problem sets](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/) that a bunch of us had expressed interest in going over on Friday. While we were talking, RS jumped in and a bunch of us ended up going into one of the RC rooms to go over the first two chunks of the problem set. It ended up being super fascinating - a ton of my heuristics about time complexity were wrong or slightly off, and there were a ton of moments where I thought I knew the answer but it turned out I didn't. LW, the guy who started the group in the first place, ended up having a bunch of really interesting proofs, visualizations, and intuitive explanations that really turned my instincts upside down.

Finally, there was a workshop on pair programming where we got to pair with another Recurser on [refucktoring](https://www.urbandictionary.com/define.php?term=refucktoring), or trying to take a perfectly innocent piece of code and turn it into a giant chunk of garbage. The problem I paired with ER on was [Armstrong numbers](http://exercism.io/exercises/python/armstrong-numbers/readme). We accidentally swapped a couple of times, but I think it was an interesting experience - maybe a bit too silly to actually be useful in the future though.

Here's the beautiful, sweet, innocent code we started with:

```python
def isArmstrong(num):
  arr = str(num)
  armstrong_sum = 0

  for c in arr:
    armstrong_sum += int(c)**len(arr)
  
  return armstrong_sum == num
```

Here's what we ended up with:

```python
import hashlib

dict = {'True': False, 'False': True}

def q(i, dict):
  z = i

  r = []

  i = str(i)

  while int(i) >= 10:
    r.append(int(i) % 10)
    i = str(int(i) // 10)

  r.append(i)

  r2 = []

  for x in range(1, len(r)+1):
    r2.append(r[-x])

  r = r2

  v = 0

  for j in r:
    y = int(j)
    while y < int(j) ** len(r):
      for p in range(int(j)):
        y += 1
    while y != 0:
      v += 1
      y -= 1
        
  if v == z:
    return dict['False']
  elif v != z:
    return dict['True']
  else:
    return 45
```

Brutal.

I feel like this wasn't that useful though because it was so counter-intuitive - making code gross is fun but I feel like the pros of pair-programming aren't that apparent while you're doing it.

Also I spent a ton of time just getting re-acquainted with the project and [Armadillo](http://arma.sourceforge.net/), a linear-algebra library for C++.

I feel like I didn't get to learn much of anything very deeply today, maybe because I spent the first half of the day coding and trying to get back into the language - semi-colons and braces suck!

### What I learned
* Some new ways of thinking about complexity
* A bit more background on functional programming
* Nothing???

### Interests/Stuff to Work On
* Rubocop for Metasploit
* Machine-learning client for Parallel Actors - reinforcement learning?
* Problem Set 1 of the [MIT Algos course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/)
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Something in OCaml??
