---
title: "Premature Optimization"
date: 2018-02-28T10:43:21Z
---
I don't really know what's happened in my life to bring me to this point but I'm currently writing this blog post at 6 AM after another incredibly successful occult working group.

I mean, I'd love to blame it on that, but it's most definitely more a result of my extremely bad decisions and odd resolution to always write blog posts the day they should be written and no later.

So.

Here we are.

RC starts again in like 3 hours.

Nice.

### General Thoughts
Today was awesome! I got a lot of stuff done, most of it incredibly stupid, which only added to the charm.

LS organized a great set of non-technical talks, and I also had some very fulfilling social programming experiences! I actually think the main reason I enjoyed them so much was because they were pretty pointless and extremely silly, which is always a winning combination.

Of course, tonight was also the second meetup of the mysterious occult working group... I feel like another Mephistophelian website may have materialized on my occult subdomain...

### What I did
I spent most of the first chunk of the day firming up some endpoints for the mock server and implementing polling functionality for [open-splendor](https://github.com/farkwun/open-splendor).

I'm starting to get really close to that sublime moment in a project when I know exactly what I'm going to do and how I'm going to implement it, but it's not quite there yet.

Anyways, who cares about that stuff, today was non-technical talks! As per usual, there were some fantastic talks, and everyone had really interesting things to say.

I've been trying to think of a non-technical talk of my own, but I'm rapidly realizing that I don't have any actual skills or hobbies, so that might end up being a bit challenging.

* AK presented more of her artwork exploring [racial impostor syndrome](https://medium.com/@saramargalb/racial-imposter-syndrome-e66aacec61de) and food, specifically focussing on a performance-art-like exhibit inspired by [mukbang](https://en.wikipedia.org/wiki/Mukbang). Mukbang is a type of video-stream where the 'host eats large quantities of food while interacting with their audience'. The twist is, AK wants to do it wearing a terrifying headpiece lined all over with teeth. She brought it in! It's disgustingly amazing - even if the teeth are only crowns and not real.
* VRC did a surprisingly interesting talk on the history and '[EVO](https://en.wikipedia.org/wiki/Evolution_Championship_Series)lution' of the [FGC](https://en.wikipedia.org/wiki/Fighting_game_community), or fighting game community, despite already having some familiarity with the subject matter. Also, I found out that he once was the best [BlazBlue](https://en.wikipedia.org/wiki/BlazBlue) player in the entire country!!
* AB gave a charming talk on the [Taungyyi fire balloon festival](https://www.go-myanmar.com/taunggyi-fire-balloon-festival) in Myanmar
* EM did a combination talk and demo on how to learn to juggle! Some tips include taking things one step at a time (don't try to juggle all at once! It's okay to practice a single movement (like a single throw, no catch) until you're comfortable enough to move on)
* KDM presented on how to save for retirement and set yourself up to retire early (like taking advantage of your company's [401k matching programs!](https://en.wikipedia.org/wiki/Employer_Matching_Program)
* CF did another excellent talk on cool bird facts. As per before, this talk did not disappoint. Some top facts:
  * The incredible [migration distances of the Arctic Tern](https://news.nationalgeographic.com/news/2010/01/100111-worlds-longest-migration-arctic-tern-bird/)
  * How [asymmetrical owl ears](https://biology.stackexchange.com/questions/67167/are-the-asymmetrical-positions-of-owl-ears-consistent-across-species-with-this-t) allow vertical sound triangulation as well as horizontal
  * A [bird that has co-evolved a habit to lead humans to beehives in order to profit from any leftover honey](https://en.wikipedia.org/wiki/Greater_honeyguide)
  * [Anting](https://en.wikipedia.org/wiki/Anting_(bird_activity)), a behaviour in which birds will cover themselves in insects
* KD gave a great talk on bees and decision-making by [dance consensus](http://news.cornell.edu/stories/2006/04/honeybee-decision-making-ability-rivals-any-department-committee) 
* MR gave a pretty interesting talk on how to sort your books, with a heavy emphasis on the *your*. The resolution of the talk was a description of her own book-sorting system, which is an eclectic combination of graph theory, personal history, anecdotes, practicality, and cat-bookshelf-napping accommodations.
* NL did a talk on the many benefits (and some cons) to biking in New York - she also mentioned [this somewhat infuriating Twitter account - @CopsinBikeLanes](https://twitter.com/copsinbikelanes?lang=en)

Non-technical talks were super cool, and afterwards I got to relive my old electrical engineering glory days when I got to talk to AK about one of her blood battery circuits. It's honestly incredible that her homemade blood batteries were able to generate enough voltage to drive a [555 timer](https://en.wikipedia.org/wiki/555_timer_IC) and light an LED.

It sounds like some people were interested in me giving a talk on writing plays, but I think I might instead do a talk on the [Iron Ring ceremony](https://en.wikipedia.org/wiki/Iron_Ring), which is very much not a thing in America.

At the very least, nobody will be able to call me on it if I get stuff wrong.

Afterwards, I happened to walk by NL's desk and started talking about his [median filter](https://en.wikipedia.org/wiki/Median_filter).

So began an incredible odyssey of delightfully premature optimization, pulling in a sizeable portion of RCers, all bending their minds to the unnecessary optimization of a potentially temporary piece of code.

The basic idea of a median filter is that, for every pixel, create an array of all of its neighbours' values and its own (9 values in total). Once you have that array, find the median value and replace the pixel with that median value.

Sounds simple - and it is - but there was a catch! In NL's implementation of the filter, it was taking around 50ms to render a frame.

NL's algorithm was simple - create the array of values, call the [standard sort from the C++ standard library](http://en.cppreference.com/w/cpp/algorithm/sort) on it, then just access the middle element to find the new pixel value.

When we removed the call to std::sort (and just grabbed a random value from the array, essentially), the time per frame went from 50ms to 15ms.

That means that this tiny 9-element sort was ballooning the time per frame over 300%!

Hence, the problem, and hence, 6 or 7 really smart people all crowding around and trying all kinds of dumb (and genius!) optimizations and seeing what stuck. The best part was, NL wasn't even sure if he was going to keep that code around, and the specific function was just a tiny piece of a much larger application.

Sounds like the perfect place to do some [premature optimization](http://wiki.c2.com/?PrematureOptimization).

It started off as just myself, NL, KDM, and RH, but quickly drew in more and more people once they realized what a great problem we were working on (made even more great by how unnecessary it all was).

I started trying to think of some asymptotically more optimal solutions than the classic [NlogN](https://en.wikipedia.org/wiki/Comparison_sort#Number_of_comparisons_required_to_sort_a_list) worst case time-complexity.

My first idea was to use a [priority queue](https://en.wikipedia.org/wiki/Priority_queue) to grab the 5 largest numbers and return the 5th largest (by definition the median), but this was the best example I've seen so far that reminded me that what's asymptotically better isn't always what's practically better.

Plugging in my heap-based priority queue implementation gave us a staggering 150 ms per frame. Uh oh.

The most successful idea I had was to run only 5 iterations of [selection sort](https://en.wikipedia.org/wiki/Selection_sort), which gave us a time-per-frame of 40 ms - an improvement, but not good enough. Not for RC.

It was interesting seeing how a theoretically less efficient algorithm could give better runtimes under the constraints provided, but I wasn't too surprised. After all, selection sort is one of the simplest algorithms there are, and I'd imagine the ~45 operations being done per 9-element array was much better than the potentially ~81 that would have to be done if I just sorted the entire array.

KDM tried to put together an implementation of [counting sort](https://www.geeksforgeeks.org/counting-sort/), but it was ultimately RH and WAC that found the most ballin solution.

The solution they put together leveraged a simple observation that launched an incredibly simple and deeply satisfying solution - because all comparison-based sorting algorithms are, almost by definition, nothing more than a series of comparisons and swaps, it should be possible to find the optimal, minimal number of swaps and comparisons necessary to create a sorted array given a small enough input.

Enter [sorting networks](http://pages.ripco.net/~jgamble/nw.html). Enter any sufficiently small array size, and the linked tool will generate a list of index tuples - compare each tuple, swap if the left value isn't smaller than the right, and at the end of all the comparisons and swaps, the array should be sorted.

Incredible!!

The highlight of the evening was definitely watching WAK and RH pair on a Python script that took in sorting network tuples to generate comparison if-statements in C++.

So convoluted.

They plugged in their massive block of if-statements and we all waited with bated breath to see the new performance... a *blistering* 30 ms per frame!!

But they weren't done. They observed that, as we are only interested in the 5th index of the array, any comparison that doesn't directly affect the 5th index after it's been placed can be deleted. They did a cursory scan to remove those statements, and we ended up with an incredible 27ms per frame.

What an adventure.

Of course, immediately afterwards, we had the occult working group, and though much of the group itself was a fugue of text-to-speech and feedback-generating [Signal](https://signal.org/) calls, I was granted with a vision of heat, and rain, and devilish incantations.

When I finally came to, there was another [incredibly odd site on that subdomain that appeared last week](https://occult.bryan-chu.com/ana/)... headphones recommended...

### What I learned
* [Sorting networks](http://pages.ripco.net/~jgamble/nw.html)!!
* Super sick birds and bees facts (I'm certain LS put these two presentations next to each other on purpose) 
* I live in two worlds, the one I see in the light of day and it is pure and bright but each time I blink an endless, endless, infinite moment of brimstone and flame and heat and heat and heat and heat and I cannot but I can I am filled but what is this I can't don't won't close my eyes my eyes my eyes my eyes my eyes my eyes my eyes

### Interests/Stuff to work on
* Splendor in React!
* [MIT OS course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/)
* Code up Knapsack problem!
* CTF!
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Kubernetes!
* MongoDB!
