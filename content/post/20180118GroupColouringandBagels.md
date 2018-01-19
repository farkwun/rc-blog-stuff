---
title: "Group Colouring for Serious Adults"
date: 2018-01-18T04:51:36Z
---
We went to the super famous [Russ & Daughters](http://shop.russanddaughters.com/) today - a smoked salmon, bagel, and pastry shop established in 1914. I got a veggie cream cheese everything bagel with onions, tomatoes, and capers. It was incredible. 

Of course, it goes without saying that this expedition necessitated its very own Zulip stream at RC - and it wouldn't be an RC adventure without someone linking some esoteric article about bagels.

The only twist is that this time, the weird, esoteric article is on **Wikipedia** - [check out this article on everything bagels](https://en.wikipedia.org/wiki/Everything_bagel). Don't tell the editors or they'll ruin it.

There was another event at RC today as well, so not only am I full of bagel, I'm also packed to the gills with pizza. My kind of day.

### General Thoughts
So, perhaps unsurprisingly, my entire morning was dominated by bagel feelings. I got in late, which normally would mean I'd miss interview prep, but it turns out the guy who normally leads it was late so it didn't happen anyways - time for some good ol' opportunistic vindication. I honestly can't even remember what I did between eating the bagels and having the [fast.ai](http://www.fast.ai/) study group meeting at 2pm. 

It can't have been that important.

I was all set to feel gross and unproductive today, but I bit the bullet and actually started coding up the React components for the Splendor app! My mind is on fire with all my next steps and possible design decisions. I guess I just had to get going.

In retrospect, today was super great - I did a lot, I had some good conversations, and some cool RC stuff happened. Check it out.

### What I did
Bagels aside, PC pulled down the [CSV NMIST digit dataset from Kaggle](https://www.kaggle.com/c/digit-recognizer) and [wrote a quick gist](https://gist.github.com/mrcoles/3b5c536a393b31f08de1546c91ab2660) to convert them all to .PNGs. He even split them up into the right directories and created a train and validation set out of the image files - what an awesome guy.

With the images all set up, it was really easy to plug the images in and experiment with different neural net architectures and play around with the weights. I spent my time post-breakfast putting together a Jupyter notebook to train our digit classifier.

[Pytorch](http://pytorch.org/) is seriously, seriously magic. With a few tweaks I was able to get the model up to 99% accuracy, trouncing a hypothesis of ours that [Resnet34](https://arxiv.org/abs/1512.03385) might not generalize well to such non-standard images.

Honestly, it was pretty much drag-and-drop.

The actual study group conversation was also really great - we went over some of the key concepts like [activation functions](https://en.wikipedia.org/wiki/Activation_function) and [the variations of stochastic gradient descent](https://machinelearningmastery.com/gentle-introduction-mini-batch-gradient-descent-configure-batch-size/). I found it really odd that [ReLUs](https://en.wikipedia.org/wiki/Rectifier_(neural_networks)) are used as activation functions for the [perceptrons](https://en.wikipedia.org/wiki/Perceptron) - it's not a differentiable function, so how is it used in backpropagation? Apparently, though, its undifferentiability at x = 0 doesn't really matter. [Quora to the rescue](https://www.quora.com/Why-does-ReLU-work-with-backprops-if-its-non-differentiable).

Anyways, I think we all came away with a stronger understanding of neural networks for machine learning, even though it was just review for the most part.

After the meeting, I finally started coding up my React components! I'm so excited - I'm still buzzing with energy to attack the application, even though I spent like 90 minutes prematurely trying to script up and standardize my deployment process. After bashing my head against the wall for an hour and a half, I *finally* realized I should probably be more worried about the application itself before I stress out trying to figure out literally the last thing I'm going to have to figure out.

We also had our weekly feelings check-in at RC (most people don't attend). It helped make me feel less anxious and shitty. I think I'll keep going to them.

Anyways, as you might recall, Thursdays are presentation days at RC! Everyone's working on really cool stuff.

* PABC made a very convincing phishing proof-of-concept leveraging the [target=_blank vulnerability](https://dev.to/ben/the-targetblank-vulnerability-by-example) to use malicious links to edit the originating context of a user's browser. The best/worst part is, he showed that Zulip still has this vulnerability in its user-supplied links - furthermore, he was able to pull down the RC login page and put up a mock phishing version as a redirect. Better clean up those user inputs.

* CF did a Part 1 on [Meltdown and Spectre](https://meltdownattack.com/), two classes of hardware vulnerabilities that subvert a number of security assumptions built into modern architectures. He didn't go as deep as I would've liked - but I suppose that's a discussion for Part 2.

* TT showed off a quick utility he built to visualize [CocoaPods](https://cocoapods.org/) dependency structures in an interactive graph.

* AK presented her blog (built on [Flask](http://flask.pocoo.org/)), the [interactive Flask debugger](http://werkzeug.pocoo.org/docs/0.14/debug/), and some insights on [git aliases](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases).

* AR finally got to present her patience-defying CSS code to create an octopus emoji with only [linear- and radial- gradients](https://www.w3schools.com/css/css3_gradients.asp). I have so much more respect for CSS.

* JK made a spitfire demonstration on his attempts to subvert the [HQ Live Trivia Game show on iOS](https://itunes.apple.com/us/app/hq-live-trivia-game-show/id1232278996) and make some quick cash.

The presentations were great, but the day was not over yet.

AB and RGS led a workshop about programming, math, group theory, and colouring! Most of the content of their presentation is available at an awesome online colouring book they wrote [here](http://www.coloring-book.co/#!/?pageName=cover&pageNumber=0). They also have a [GitHub repo and they want pull requests](https://github.com/aberke/coloring-book).

Some stuff they covered:

* [Frieze groups](https://en.wikipedia.org/wiki/Frieze_group)
* [Transformation geometry](https://en.wikipedia.org/wiki/Transformation_geometry)
* [The Alhambra tiles in Spain](https://en.wikipedia.org/wiki/Alhambra) and the incredible fact that their designs encompass all [17 mathematically possible wall-paper groups](https://en.wikipedia.org/wiki/Wallpaper_group). Escher studied and drew from these tiles to make [his tesselations](https://en.wikipedia.org/wiki/M._C._Escher#Tessellation).
* Colouring in and creating your own wall-paper groups with grid paper and pencil crayons!

It was surprisingly relaxing trying to draw shapes with transformation geometry. I much preferred it to regular drawing. I didn't colour any of mine in, but that was mostly because they were absolutely dreadful.

### What I learned
* Intro to Group Theory
* How to draw wall-paper groups!
* Some fast.ai utilities
* Sometimes you gotta just start the damn project

### Interests/Stuff to work on
* Splendor in React!
* SHOW UP FOR MORNING ALGORITHM PREP
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
