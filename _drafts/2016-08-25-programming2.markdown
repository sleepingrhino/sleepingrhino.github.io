---
layout: post
title:  "On programming 2"
date:   2016-08-25 12:00:00 +0200
---






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
virtual machine did not define nor allow for such anomalies.

We effectively broke our equivalence promise.

So we changed the internal model of the fantasy machine.

