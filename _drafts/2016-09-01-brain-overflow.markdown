---
layout: post
title:  "Brain Overflow"
date:   2016-09-01 13:42:00 +0200
---

Today I want to talk about the requirements that we have for programming languages. For the thought experiment I looked at them from different perspectives:

First I put on my web-developer hat. From this view, a language has to provide *developer productivity*: I want to build my business logic fast and easily changeable without worrying to much about technical details. Furthermore we want a toolbox of language development techniques with things like meta-programming/makros, reflections, list comprehension, control-flow instructions (foreach, ...) to *express* our problem. At the same time we want languages that restrict our view of the machine in order to give us *guarantees* about program behaviour (one example being garbage collection or types) and frameworks that separate our platform from the business logic (*separation of concerns*). So when this is our goal when looking at languages, we don't we all use a statical typed lisp already? (by the way: [thats a thing](https://docs.racket-lang.org/ts-guide/)!)


The answer is that we still need a way to map higher level languages to our systems. When we switch hats to a system developer view, we see that our goals change drastically. We want a low level view of our available hardware, in order to use it efficiently. We want to use 'smart' optimizations of higher order constructs (for example write reordering). We want to explicitly connect to other hardware interfaces on a byte-level. **But** what we don't want, is to adapt our language every time a new piece of hardware is built. So on the lower level we need some kind of abstraction too!

<!-- TODO unix, conclusion -->
