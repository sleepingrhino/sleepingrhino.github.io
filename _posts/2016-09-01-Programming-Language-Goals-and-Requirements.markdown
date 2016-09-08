---
layout: post
title:  "Programming Language Goals and Requirements"
date:   2016-09-01 13:42:00 +0200
---

Today I want to talk about the requirements that we have for programming languages. For the thought experiment I looked at them from different perspectives:

## Trade-off high vs low level

First I put on my web-developer hat. From this view, a language has to provide *developer productivity*: I want to build my business logic fast and easily changeable without worrying to much about technical details. Furthermore I want a toolbox of language development techniques with things like meta-programming/makros, reflections, list comprehension, control-flow instructions (foreach, ...) to *express* my problem. At the same time I want languages that restrict my view of the machine in order to give me *guarantees* about program behaviour (one example being garbage collection or enhanced type systems) and frameworks that separates my platform from the business logic (*separation of concerns*). So if this is the goal when looking at programming languages in general, why don't we all use a statically typed lisp already? (by the way: [thats a thing](https://docs.racket-lang.org/ts-guide/)!)


The answer is that we still need a way to map higher level languages to our systems. When we switch hats to a system developer view, we see that our goals change drastically. We want a low level view of our available hardware, in order to use it efficiently. We want to use 'smart' optimization of higher order constructs (for example write reordering). We want to explicitly connect to other hardware interfaces on a byte-level. **But** what we don't want, is to adapt our language every time a new piece of hardware is built. So on the lower level we need some kind of abstraction too!

<!-- TODO unix (HAL, udev, treiber) -->

## The two levels of concurrency models
When we look at current developments in the space of concurrency models, we see a similar pattern: To build big concurrent or distributed application we rely on **message passing** or **immutability** to ensure the safety of our system. Two examples for this are [unix pipes](https://en.wikipedia.org/wiki/Pipeline_(Unix)) (copy semantics) and [erlang](http://learnyousomeerlang.com/introduction#about-this-tutorial) (immutable data). But copying data comes with memory and runtime overhead that may be too much for a performance critical application. So on the low level, we use a **shared memory** approach to concurrency, to bypass the overhead (leading to data-races and other shared memory bugs).

One interesting approach driven by languages like [rust](https://www.rust-lang.org/en-US/) or [pony](http://www.ponylang.org/) is the idea to reduce performance overhead by introducing **move-semantics** and thereby limiting *shared* mutable state while preserving mutability. The idea is to invalidate data that is given to another thread of execution in the original thread. One potential problem that I see with this is that because the compiler has to check the whole system for errors this approach may not scale to big code-bases (please correct me if I'm wrong!)

Another approach to enable safety-guarantees in a shared-memory setting are [algorithmic skeletons](https://en.wikipedia.org/wiki/Algorithmic_skeleton) (or structured parallel patterns): To ensure data-race free programs the model is to use fixed parallelism structures similar to the approach of structured programming (use for/while/if instead of GOTO). The most famous examples is the parallel map skeleton (evaluate a function on each object of a collection in parallel). The idea is to write sequential functions, that are parallelized by the skeleton library/system.

## Summary
We see that due to the trade-offs between developer productivity and performance in the single-threaded case and safety and performance in the multi-threaded case different languages try different models to achieve different goals. So if you don't want to simply mash all the models together (and I doubt you can without problems) there is no one-size-fits all approach to languages. My quarrel with the whole thing is the **interoperability**: Why don't we have an ecosystem that supports different styles of programming languages for different levels whilst preserving *inter-language guarantees*?

-MM