---
layout: post
title:  "On programming 2 : language boundaries"
date:   2016-08-29 12:00:00 +0200
---

In the [last post](http://www.sleepingrhino.com/2016/08/25/progamming1.html)
we established that the programs we write are for an abstract machine.
So what are the basic building blocks that imperative languages give us
for programming that abstract machine?

Let's take a look at a language like C for instance. What can we do in C programs?
What basic concepts are there?

Well to me these are the basic concepts available:

* arithmetic, logical and relational operators
* control flow, branching and looping
* variables
  * referenced via name or address
  * assignment (reuse)
  * compose structs from built-in types
* functions, function calls

So looking at that list and keeping the abstract machine thing in mind,
I hope the answers to the following questions don't come as a surprise.

How do you...

* read user input? You can't.
* write to the screen? You can't.
* write to a file? You can't.
* connect with a host via internet? You can't.

All you can do is calculate something using basic maths, loops and
if-branching, use variables to store, name and reuse results and
separate your code into functions and call them using your variables
as parameters which are either copies of their values or their addresses
depending on whether you want to work in place or not.

This is great because this *is* computation. This is the bread and butter
that gives you Turing completeness and allows you to express *any*
computation imaginable.

This is also what is completely irrelevant for most
applications today.

So how do you do all those things we usually do? How do you read user
input and write to files or connect to a host over the internet?
Well...you call a library function. A library function that somehow
does what you want, sort of like a side effect. It's almost like a foreign
function interface but with the interface being the API of your operating
system (POSIX?).

You can easily see that because how do you identify a
*system call* in a C program?

    int main() {
      a();
      b();
      c();

      return 0;
    }

Which one's the system call?

There's no way to know because the language has *no idea* about system calls.
As it has no idea about files, sockets, hosts or ports or *anything* else ...
and that's fine.

But it's also something you need to keep in mind because we are building
incredibly complex, distributed systems **today** using tools and languages
from a time in which we were happy we could even program at all.

Maybe it's time to think about whether or not this should change.

\\
-FL
