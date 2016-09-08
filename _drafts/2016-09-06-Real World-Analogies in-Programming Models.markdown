---
layout: post
title:  "Real World Analogies in Programming Models"
date:   2016-09-07 13:53:00 +0200
---

During the last year i had many interesting and thought provoking discussions with my office-mate about the fundamental nature and the process of programming. This lead to ideas regarding the design of programming languages and concepts, which i like to share with you:

Currently a lot of research and interest is going towards handling complexity in programming. But what exactly is complexity? In my opinion there are two representative approaches to the problem: On the one side, **Rich Hickey** tries to build his own understanding of complex as the opposite of *simplex*: complex structures are intertwined things, that require us to think about more than one aspect of a program at the same time (see his famous ["Simple made Easy"](https://www.infoq.com/presentations/Simple-Made-Easy) Talk). On the other side **Chris Granger** expands the ideas of Bret Victor by trying to make programming eay enough for everybody to understand (see his ["In search of Tomorrow"](https://www.youtube.com/watch?v=VZQoAKJPbh8) Talk at BIDS).

The Rich Hickey approach (although much greater than that) reflects a current trend of using functional languages in enterprise/web-applications. The rationale behind this is that stateful programs introduce heaps of complexity and are hard to reason about.

<Hier fehlt etwas>

Yet many people struggle with the functional programming approach.
Why is that the case?
My hypothesis is that this comes from a cognitive mismatch: Math doesn't work like the real world.






------------------------------------------------------


 Der Rich Hickey Ansatz spiegelt einen Trend wieder funktionale Sprachen zu verwenden. Eine Rechtfertigung dafür ist das Komplexität durch statefulness induziert wird. Aber viele leute struggle with functional progamming.

 Warum ist das so? Meine These: Mathe funktioniert nicht wie "die echte Welt". Die echte Welt ist inherently stateful. Flaschen-Beispiel? Und auch unsere Computer sind stateful: Im lokalen Beispiel RAM, Display, Maus, im cluster: zustand der Rechner =>> Die Interaktion eines Programms passiert mit stateful Dingen. 

 Außerdem: Objektorientierung scheint vielen Leuten zu helfen -> große Adaption des Paradigmas

 Taking a step back: What are Problems when programming? What is "complexity"?

 Wir lösen komplizierte Probleme (bsp Webanwendung und sämtliche Use-Cases davon). =>> Abstraction

 Ein großes Problem der statefulness in Objektorientierten Sprachen ist die unbounded-ness: Beliebig viele Leute können eine Referenz auf ein mutable Objekt besitzen! Das macht das reasoning so schwer, vor allem in nebenläufigen settings.

 How do we solve this in real life? => Beispiel in der Echtwelt: Anrufbeantworter + Synchronisierung

 Wenn man sich die Erkentnisse von Chris Granger anguckt: Leute haben Probleme mit "Scoping": Teil des Perception Problems?

 Und ein weiterer Aspekt von Perception: Identity! How are "things" in computer programs adressed, auseinandergehalten und welche Semantik hat ein Name in einem Programm?

Was bedeutet instantiation eigentlich wenn wir es auf die physische Welt abbilden wollen?

 
