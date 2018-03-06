---
title: "Data Entry"
date: 2018-03-02T22:30:06Z
---
I broke my promise of only blogging the day of!

But only sort of. I ended up staying at RC until 5 AM last night, and technically that's today so...

### General Thoughts
Yesterday was great!

I ended up staying in at RC very very late, but I did so because I had a lot of momentum going for [open-splendor](https://github.com/farkwun/open-splendor).

The first chunk of the day was pretty super unproductive though - I missed out on the first meeting of a new course people are doing at RC, [Seven Languages in Seven Weeks](https://geneticmail.com/scott/library/text/seven-languages-in-seven-weeks_p1_0.pdf).

That said, the first language was Ruby so I feel at least somewhat okay about skipping out on it.

We also ended up doing some work on the [Pragyan CTF](https://ctf.pragyan.org/home), which was cool but not very rewarding - I barely got anything done on it and just ended up being confused.

The second half was way better!

### What I did
So besides buying and eating a ton of super cheap and delicious Chinese food, almost nothing got done until the evening half of the day.

The CTF we were working on was interesting academically - I learned some more [GDB](https://www.gnu.org/software/gdb/) and low-level-ish tricks, like setting breakpoints at memory addresses and using [objdump](https://en.wikipedia.org/wiki/Objdump) to get the [assembly](https://en.wikipedia.org/wiki/Assembly_language) for a given binary.

The binary we were working with took a string as input and did a [strncmp](http://www.cplusplus.com/reference/cstring/strncmp/) to compare the input string with some password, and JE found a hilarious way to use [ltrace](http://man7.org/linux/man-pages/man1/ltrace.1.html) to just directly output the arguments passed to the string comparison. 

I guess the CTF designers thought we might do that though, because finding the password to the binary was just step one of the challenge! I didn't end up figuring it out, but another group in the space did.

I'm going to get them to explain it to me!

Afterwards, I started going through the [Ruby](https://www.ruby-lang.org/en/) chapter of the Seven Languages textbook, and I actually got a somewhat better understanding of [duck typing](https://en.wikipedia.org/wiki/Duck_typing).

Despite it placing me behind, I do think it might be worthwhile to read the entire chapter and do the exercises, as there are definitely some [fairly unique Ruby idiosyncracies](http://www.railstips.org/blog/archives/2008/12/01/unless-the-abused-ruby-conditional/) that seem worth at least considering. 

That said, we're apparently moving onto [Io](https://en.wikipedia.org/wiki/Io_(programming_language)) next week, and I should prioritize new stuff for sure!

It's also a [prototype-based language](https://en.wikipedia.org/wiki/Prototype-based_programming) like [JavaScript](https://www.javascript.com/), which is a concept I barely understand, so hopefully I get my stuff together enough to be able to jump in on that coursework.

For the first time in like three weeks, I actually made it out to programming interview prep Friday - this time I was an interviewer!

It seemed like the newer crop is a bit less comfortable with programming interviews in general, so I decided to go with [string compression](https://leetcode.com/problems/string-compression/description/) (though not in-place) and [creating all permutations of a unique string](https://stackoverflow.com/questions/4240080/generating-all-permutations-of-a-given-string).

The process of interviewing was really fun, and I was surprised to actually be providing some amount of value in an RC event for once!

On a whim, I also decided to start going full office-job and finally do all the data entry for the cards and nobles in [Splendor](https://en.wikipedia.org/wiki/Splendor_(board_game)). It was surprisingly easy, and I got to flex some very, very old Excel muscles (though technically it was all in [LibreOffice](https://www.libreoffice.org/).

However, that gave me a bunch of momentum to write some dinky [Python](https://www.python.org/) scripts to parse the Excel [CSVs](https://en.wikipedia.org/wiki/Comma-separated_values) - in fact, I was inspired by the hilarious Python-to-Javascript code that WAK and RH wrote for premature optimization last Wednesday, and used Python to generate usable JavaScript constants for open-splendor.

That led me to re-leverage those scripts to generate static data for the mock server in [Flask](http://flask.pocoo.org/) and, by the time I actually left RC last night I've gotten the front-end almost completely ready to go.

All the components are complete, and the only things left to do now are to break out the game logic I wrote into the client-end application into the server-side and actually track who the current user is (right now each client gets a playable version of the game, when user actions should only be possible if its your turn).

That said, the mock server is steadily growing more and more spaghetti-fied and disgusting, but who cares? I'll be throwing that away soon enough to do some more serious API design in [Golang](https://golang.org/).

### What I learned
* A slightly better understanding of [duck typing](https://en.wikipedia.org/wiki/Duck_typing)
* Cool low-level analysis tidbits
* I'm still solid at data entry - time for a career change

### Interests/Stuff to work on

* Splendor in React!
* [Seven Languages in Seven Weeks](https://geneticmail.com/scott/library/text/seven-languages-in-seven-weeks_p1_0.pdf)
* [MIT OS course](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-828-operating-system-engineering-fall-2012/)
* Code up Knapsack problem!
* CTF!
* [fast.ai](http://www.fast.ai/)
* Something in Prolog??
* PICO-8?
* Something with compilers? Maybe just the lexing and parsing side?
* Kubernetes!
* MongoDB!
