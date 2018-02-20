---
title: "Non-Technical Talks Part 2!"
date: 2018-02-13T05:40:58Z
---
I'm sure it's starting to get pretty old hearing about my sleep schedule but it's pretty notable how awful its getting - I think I made it into RC today at 1pm, and I couldn't fall asleep last night until something like 4 AM.

What a mundane descent - couldn't I at least have had the common human decency to slip more dramatically until slovenliness?

I'm at RC tonight at 12:45 AM, having stayed late to conduct a mock interview for a friend, so it really seems like this cycle will continue.

### General Thoughts
I had once counted caffeine among one of my most potent secret weapons, however today I really felt the backlash. I must have spent 2-3 hours buzzed out of my mind, which isn't the best mental state for learning something like [Redux](https://redux.js.org/).

That said, today I got back to full functionality on [the Redux branch of open-splendor](https://github.com/farkwun/open-splendor), so that's something. I'm realizing, though, that the way I've been refactoring and migrating to Redux hasn't really improved on the original design decisions I made weeks ago - I'm worried that I'm painting myself into a corner with some of the ways I've chosen to structure my application.

I think I'm going to need to do a more clear-headed review of the system tomorrow and determine if I'm not just adding more and more cruft through these additional libraries.

I also don't really feel like I learned all too much today - for the most part I found myself getting stuck on best practices and style more than implementing any particularly novel concepts, even if I definitely have a stronger understanding of [how data flows through the store](https://redux.js.org/docs/api/Store.html).

I really feel like waking up super late every morning and staying up super late in the evenings is really messing up my ability to stay sharp and do good work. I'm not sure how to fix the issue though, because its currently 2:59 AM and I'm still writing up this post at RC.

### What I did
The strictly Redux portion of open-splendor is technically finished, in that we've successfully migrated data to the store, but I still feel like the overall structure of the application hasn't changed. 

For that reason, I don't really feel like I've gained all that much through the addition of Redux, though perhaps a part of that is how I've structured my application. It's feeling increasingly likely that I've made some fundamentally wrong decisions that are now fairly deeply entrenched into my application logic, and I've been too fuzzy and sleep-walk-y to suss it out.

Writing this now, however, I think a part of my discomfort with adding Redux is that it feels like my state logic has become so decoupled that it's actually starting to become hard to reason about what's going on - the precise oppposite of [Redux's promise](https://redux.js.org/docs/introduction/Motivation.html). I'm choosing to attribute some of that to my sleepy-wired mental state, but I need to figure out how the process of cascading actions through reducers like this isn't just a ton of work for not that much payoff.

Maybe [middleware](https://redux.js.org/docs/advanced/Middleware.html) is the answer. It is the final piece of the puzzle, after all. I'm pretty embarassed that I've been writing about middleware as if its an actual library, when I've recently been informed that it's really just a pattern that libraries like [thunk](https://github.com/gaearon/redux-thunk) actually implement!

Oh well. I already said I'm not editing these.

Also, we finally had the second half of our non-technical talks today! Just like last time, there were some fantastic presentations, though I'm not sure anything is going to top LW's talk on Why New York Water is so Delicious (it's actually the most delicious water I've ever had, from a tap or otherwise).

Here were the presentations:

* AL gave a talk about his experience with the "carnivore diet" and how it helped him reach his weight and fitness goals. He touched on nutrition, personal experience, and even his bowel movements, which I assure you was quite delightful.
* JF gave a talk on "Karaoke Theory", or how to maximize the enjoyment of yourself and the people around you during a night of karaoke. It was a surprisingly sincere presentation, dealing with subjects like the transformation and loss of the shared experience of communal singing. He didn't actually sing any songs though!
* SE gave a rousingly ambitious talk on the entire history of Rome in 5 minutes - 250 years per minute!
* CF gave a presentation on cool bird facts from his work in the ornithology department of his college! Some of my highlights:
  * The [iconic bald eagle screech](https://www.youtube.com/watch?v=WSGFatM1ktU) is actually the sound of a [red-tailed hawk](https://www.youtube.com/watch?v=77_oa_Cyw3g)! Bald eagles actually sound like [this](https://www.youtube.com/watch?v=9RArGl2vkGI).
  * [Woodpecker skull structures](https://www.birdwatchingdaily.com/blog/2013/12/10/woodpeckers-hammer-without-headaches/)
  * The [incredible endurance of the bar-tailed godwit](https://news.nationalgeographic.com/news/2007/09/070913-longest-flight.html)
* KEG gave a somewhat more pragmatic talk on How to Negotiate Your Job Offer, focussing on the art of dodging the salary expectation
* NL gave a brief, but enjoyable talk on how to "find stuff out" and stay in the loop when it comes to events and social media
* I gave a totally impromptu talk on some fundamentals of stage acting and how to break down a scene using [Antony's famous speech from Julius Caesar](https://www.poetryfoundation.org/poems/56968/speech-friends-romans-countrymen-lend-me-your-ears)! I only did it because a couple of people backed out of doing a talk at the last minute, but I'm glad it wasn't a complete disaster.

Non-technical talks were really fun! There might not be any more, as AKR (the organizer) is finishing her batch this week - I'm glad I got a chance to give one.

### What I learned
* Caffeine is a fickle mistress
* Working with reducers, actions, and dispatchers in Redux, as well as the seemingly massive amount of boilerplate that seems to go with it
* THE BALD EAGLE SCREECH IS ACTUALLY A RED-TAILED HAWK!

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
