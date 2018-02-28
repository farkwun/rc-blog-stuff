---
title: "OCCULT"
date: 2018-02-21T07:20:50Z
---
Some RCers went over some posts on my blog today and decided to go back in time to some of my earliest posts.

The post they opened mentioned coming in at 10:30 AM and wondered if it was possible to maintain that schedule.

In unrelated news, I woke up at noon today and only managed to get into RC at 1:30 PM.

Seriously though, I should probably find and remove all those posts containing my credit card number and social security info.

### General Thoughts
I'm writing this blog post at 2:30 AM from RC! I'm actually finding working in the evenings pretty productive, especially when it comes to my personal projects.

As much as I'm blatantly ruining future Bryan's life, present Bryan is having a great time enjoying some particularly odd night-time activities. Who does that stuck-up future Bryan think he is, anyways?

I've been making a specific effort to socialize with the new batchlings, and it's pretty interesting to watch some old courses get restarted. It looks like a group is going to start grinding through my old nemesis, the [MIT Intro to Algorithms course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/).

This was also by far the strangest night I've spent at RC, as a mysterious event appeared on the calendar for an 'occult working group' - sans, and beyond, description...

ALSO LS got a bunch of us to try on some [facial masks](https://en.wikipedia.org/wiki/Facial), and the space was briefly filled with Michael-Myers-style serial killers.

WITH BEAUTIFUL SKIN.

### What I did
It turns out we actually didn't finish the entire MIT course last week - there was still a [final problem set](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-006-introduction-to-algorithms-fall-2011/assignments/MIT6_006F11_ps5.pdf) on [arithmetic operations](https://en.wikipedia.org/wiki/Computational_complexity_of_mathematical_operations) and [RSA encryption](https://en.wikipedia.org/wiki/RSA_(cryptosystem)).

Specifically, the pset focussed on multiplication algorithms like [Karatsuba's algorithm](https://en.wikipedia.org/wiki/Karatsuba_algorithm) and [Newton's method](https://en.wikipedia.org/wiki/Newton%27s_method). Academically interesting but not particularly fun to analyze. The major insight was that there isn't currently a multiplication algorithm that achieves [the theoretical lower bound](https://en.wikipedia.org/wiki/Multiplication_algorithm#Lower_bounds). For some reason I always assumed there was a clever algorithm for multiplication in linear time.

Sadly, only LW and I actually showed up. Looks like the old group is ready to be done with it. Some of the new batch tried to join in, but I think it's pretty overwhelming to just suddenly jump in mid-way through a chunk of fairly obtuse MIT coursework.

It turns out both LW and I were totally awful and didn't do any work before the meeting - it turned out pretty great though. We were able to finish the entire problem set together within the time we set aside! Maybe that should have been my approach this entire time to the coursework - it's a lot more satisfying to get things done together instead of all by myself.

I also paired with PABC on [open-splendor](https://github.com/farkwun/open-splendor), specifically trying to get a better handle on [middleware](https://redux.js.org/advanced/middleware) for [Redux](https://redux.js.org/).

He's also the one who helped me set up a quick and dirty [Flask](http://flask.pocoo.org/) server to help test my front-end! It only took 10 lines and I no longer have an excuse not to move forward.

Ever since I paired with CW on that fateful Friday last week, I've been gaining a much stronger understanding of [currying](https://en.wikipedia.org/wiki/Currying) and [partial application](https://en.wikipedia.org/wiki/Partial_application), and not only that, but the *distinction between the two*. That's really starting to help a lot with figuring out how exactly middlewares like [thunk](https://github.com/gaearon/redux-thunk) are meant to interact with my Redux store.

I ended up taking another small step forward with open-splendor - actually applying thunk to my store and using it to make a simple GET request to my mock server. It works! Now that I have a somewhat better understanding of how [async](https://en.wikipedia.org/wiki/Asynchrony_(computer_programming)) is going to work, I can start working on a 'waiting room' for users to queue up in before starting games. 

In the process, I had a great conversation about [cross-origin resource sharing](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing) (or CORS) with CW, AM, RT, and KDM. At first, we didn't quite understand the specific security vulnerabilities CORS represented, especially why CORS access needs to be set on the server-side, but I think we did a fairly good job working it out. 

Something standing in the way of my own understanding was that I hadn't ever really thought about how requests made within a webpage actually get sent out, and I had only ever done API requests from non-browser contexts. For that reason, the fact that the *browser itself* is the one rejecting server responses that were not sent from the origin of the webpage was unclear to me - but it makes sense. If the browser state contains authentication cookies, and cross-origin requests were allowed by default, it might be possible for JavaScript from one web page to make requests from within a user's browser and access sensitive information from other websites using that user's authentication cookies.

This way, servers must specifically decide which endpoints are accessible from other webpages, or if those endpoints are accessible at all.

It also turned out that the majority of us had run into this issue recently, which made the conversation all the more fortuitous.

But that wasn't the real highlight. The real highlight was the occult working group... or should I say... **darklight**...

I have scattered memories of the event. All that remains are flashes of image, sound, and sensation. Moans, chants, discordant guitar music, a dark room. A monitor hooked up to an antenna tuned to the lower bound of the [smart meter](https://en.wikipedia.org/wiki/Smart_meter) frequencies in New York and piping the resultant tones through its speakers. Text-to-speech of man pages and [/usr/share/dict words](https://en.wikipedia.org/wiki/Words_(Unix)).

And finally, at the end of it all, a webpage, materializing on [one of my very own subdomains...](https://occult.bryan-chu.com/).

Who can say what has possessed the Recurse Center in these mysterious times?

### What I learned
* How to actually dispatch functions with [thunk](https://github.com/gaearon/redux-thunk)
* [CORS](https://en.wikipedia.org/wiki/Cross-origin_resource_sharing)
* Intro to multiplication algorithms 
* How to be beautiful
* How to vibrate within the computational void, the interstitial lattice, the back of the man page, [/dev/null](https://en.wikipedia.org/wiki/Null_device)...

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
* O C C U L T
