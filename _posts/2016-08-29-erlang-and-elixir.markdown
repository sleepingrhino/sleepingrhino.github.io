---
layout: post
title:  "Evaluating Erlang and Elixir"
date:   2016-08-29 14:35:00 +0200
categories: languages
---

Over the course of the last two weeks I looked at both [Erlang](https://www.erlang.org/) and [Elixir](http://elixir-lang.org/). The ideas of Erlang (namely building a language on the abstract notion of processes) are still highly valuable and inspired many of the technologies used in recent cloud development tools. Nonetheless the language has some quirks and bumps that always kind of bothered me: On the syntax side, I've never gotten around the usage of punctuation: Although Joe Armstrong explains in the'"Programming Erlang' book [1] that it is used 'similar to the use in the english language', the overloading of the comma and semicolon in guards and as function clause delimiter is something I still trip over. Furthermore I personally dislike the error messages given by the compiler as they are not very helpful in fixing the problem (TODO example). And especially in the beginning I often made the mistake of confusing atoms and variables in my source code (The difference being acapital first letter for the latter), and the compiler messages weren't very helpful either. When watching the ['Why the Cool Kids Don't Use Erlang'](https://www.youtube.com/watch?v=3MvKLOecT1I) talk by Garret Smith I found out I was not alone with some of my troubles.

### Elixir 

Some of the things I spoke about in the last paragraph are addressed by the Elixir-Language (started by José Valim): He brings the syntax closer to the ruby syntax and while doing this eliminates the punctuation problems, cleaned up logical-expressions in guards and made the distinction between atoms and variables more clear by adding a semicolon in front of every atom. Although the resulting language is still very similar to Erlang, it is nice to see somebody addressing problems on the syntax level and doing some house-cleaning with the language (apart from building a macro system etc). Cleaning up loose ends and non-used features is a task that has no glamour to it and is often overlooked in software systems and still is highly valuable to enrich the ecosystem and drive the software world forward without amassing complexity. Another thing seen in this is the importance of a clear separation between frontend and backend of a language: due to the shared beam-VM both languages are interoperable and can happily coexist in an environment without major integration problems. I think this is a pattern that is repeating itself throughout the software world (with the JVM and LLVM) that encourages heterogeneous approaches to the languages while still maintaining interoperability.


### Closing Remarks

Although Elixir feels like a step forward from Erlang, there are still some issues I've had when looking over it. Please keep in mind that my investigation of both Erlang and Elixir as languages is still in it's infancy: Problems listed here are possibly due to my ignorance of the Erlang eco-system and the capabilities of OTP.

That being said I still miss an error model for network failures in Erlang: all we can see is that a process has 'died': We have no knowledge about this death being due to a logical error or a network failure. This could be problematic when building partition-tolerant databases or when the process hasn't actually died and comes back to the network.

Furthermore the compiler errors still don't point me to the right fix (a problem that at the moment is [actively worked on in the rust community](https://blog.rust-lang.org/2016/08/10/Shape-of-errors-to-come.html)). I know that this is kind of nitpicking but it presents a barrier for developers new to the environment and therefore could hinder adoption.

Nevertheless Elixir and Erlang are both fascinating languages and I sincerely recommend checking them out when thinking about distributed systems and their development!

-MM

[1] Armstrong, Joe. Programming Erlang: software for a concurrent world. Pragmatic Bookshelf, 2007.
