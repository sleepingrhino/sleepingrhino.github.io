---
layout: post
title:  "On programming 1"
date:   2016-08-25 12:00:00 +0200
---

When you ask the question: "What is the purpose of a programming language?"
one of the more intuitive answers is to say "to allow the programmer to
program the machine". Some might even add "tell it, what to do" and I
do think that there's nothing wrong with that answer.
However,  I have often gotten the impression that a lot of people think
that this is what's really happening and I think it is crucial to understand
the subtle differences of the solution we are actually using in order to
think about programming and programming languages properly.

The way I see it, back in the day, we had single machines.
They had a single CPU core, some memory and a hard drive and we wanted
people to use/program these machines. Luckily some people came up with
a programming language and wrote down its syntax, how statements or
expressions were supposed to behave and how they composed to form
programs.

But...this programming language was not meant for a real machine.
Instead, the language was defined for an abstract, virtual, often times
even non-deterministic machine. A fantasy language for a fantasy machine.
So you could write down programs in that language, no problem, but these
programs could not be executed because the machine they were for did
not exist.

How did that help anyone?

Well, luckily the internal model of the abstract fantasy machine was
very similar to how the real physical machines worked and
so using the real physical machines, you could take the program written
in the fantasy language, parse it, turn it into code the real machine
could understand, execute that code on the real machine and therefor
*emulate* what the abstract virtual machine would do and *promise* that
all of the intermediate results of the real machine would be
*equivalent* to each intermediate result the fantasy machine would produce.

So as a programmer you are using a fantasy language for a fantasy machine
that does not exist but since the real machine on which your program is
actually executed promises to behave equivalent to that fantasy machine
it seems to you, as though you are programming the real machine.

We've created a perfect illusion which solved our problem of how to
program these real machines we had. A simple yet powerful trick.

And you can actually see that in action because the physical machines
changed over time. For instance they got multiple CPU cores so they
could execute independent parts of you program in parallel.
Unfortunately the programs we wrote could not use this new feature
because the internal model of the fantasy machine they were for
did not have such a feature and therefor the language did not
include any ways to utilize something like this.

We therefore invented libraries like the *pthread* library which allowed
to hide the parallel execution inside the real machine behind a simple
function call in our fantasy language, which looked like any other
function call.

This however, led to effects like data races because in our execution
on the real machines multiple threads would now access memory concurrently,
which led to results that, to the programmer, could not be explained when
looking at the code, because the program, the language and the abstract
virtual machine did neither define nor allow for such anomalies.

We effectively broke our equivalence promise.
So we changed the internal model of the abstract machine...

\\
What I would like for anyone who thinks about the topic of programming
or programming languages to keep in mind is that the languages which we
use to write our programs are defined on abstract, virtual and often times
non-deterministic machines and we merely implement those languages using
the hardware and possibilities currently available to us in order to
emulate the intended behavior of the fantasy machine on which they are
actually supposed to be run on.

This mind set will allow you to clearly seperate the language specification
from its implementation with all its nuances and implementation details.
It will also allow you to on the one hand think about the language itself
and what language features the programmer needs in order to express his
intent and on the other hand how to best implement those features.

\\
-FL
