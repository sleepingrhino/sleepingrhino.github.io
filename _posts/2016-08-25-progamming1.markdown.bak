---
layout: post
title:  "On programming 1"
date:   2016-08-25 12:00:00 +0200
---
The programming languages we use today are defined for an abstract,
virtual and often times even non-deterministic machine.
This abstraction allows to implement the language on different hardware
and in different ways.

But it also means, that we as programmers write programs
that cannot be executed because the languages we use to
write them are meant for machines that do not exist.

We merely try to implement those languages using the hardware
and possibilities currently available to us. So we parse the
given program, turn it into something our real machines can understand
and then execute that instead in order to *emulate* the intended
behavior of the abstract machine on which the program is actually
supposed to be run on.

This works because the internal model of the abstract machine is
almost identical to how our real machines work.
So we *promise* that our implementation on the real machine will
always deliver an *equivalent* result to what the abstract machine
would have produced.

This is a clever trick. Not only does it allow for different
implementations of the language on different hardware. It also
creates the *illusion* that we are actually programming our
real machines.

Looking at recent history you can even see that illusion crumble
because over time our real machines changed. They have gotten
multiple CPU cores which allow us to execute independent parts
of our program in parallel.

Unfortunately the programs we wrote could not use this new feature
because the internal model of the abstract machine did not have such
a feature and therefor the language did not include ways to
utilize something like this.

We therefor invented libraries like the *pthread* library which
allowed to hide the parallel execution inside the real machine
behind a simple function call in our fantasy language, which looked
like any other function call.

This however, led to negative effects because in our execution
on the real machine multiple threads would now for instance access
memory concurrently, which led to results that, to the programmer, could
not be explained when looking at the code, because the program, the language
and the abstract machine did neither define nor allow for such
anomalies.

We effectively broke our equivalence promise.
Which is why most languages have also changed the internal model
of their abstract machine over time. This might all seem like an
uninportant detail but it actually isn't.


\\
So what I would like for anyone who thinks about the topic of programming
or programming languages to keep in mind is that the languages which we
use to write our programs are defined on abstract, virtual and often times
non-deterministic machines and we merely implement those languages using
the hardware and possibilities currently available to us in order to
emulate the intended behavior of the abstract machine on which they are
actually supposed to be run on.

This mind set will allow you to clearly seperate the language specification
from its implementation and it will also allow you to, on the one hand,
think about the language itself and what language features the programmer
needs in order to express his intent and on other hand how to utilize
the hardware currently available to implement those features
as well as possible.

\\
-FL
