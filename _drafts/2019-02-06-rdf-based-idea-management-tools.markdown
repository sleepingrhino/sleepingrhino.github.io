---
layout: post
title:  "Discussing a Knowledge-Graph Based Idea Management System"
date:   2016-08-25 12:00:00 +0200
---



Idea Management Tools focus on the digitial support of capturing, managing, and collaborating on ideas. In their great DRS 2018 Article, Inie, Dalsgaard and Dow describe three challenges for current idea management tools revealed by interviews with 16 professional designers. This article looks at these three challenges from a technical perspective: The aim is to show possible approaches to these problems by the employment of knowledge graphs and triple based data formats.

### What is an Idea Management System?

Coughlan and Johnson (Coughlan & Johnson, 2008) coined the term idea management as a way of describing the various practices, creative practitioners exhibit to keep track of their ideas. They identified three main purposes that creatives try to achieve in their management of ideas: 1: retention and organizing of ideas, 2: feedback, evaluation, and development of ideas, and 3: communication of and collaboration around ideas.
In this paper, we share a similar understanding of idea management, and thus our definition of idea management tools is any tool, digital or analog, that designers use to capture and/or keep track of their ideas. When we describe idea management systems, we refer to an assembly of tools that a given designer has told us they utilize for idea management purposes.  (quote Challenges Article)

### What is a knowledge graph?
Knowledge Representation Fundamental: Fact -> SPO Triple
TODO:
* RDF
* Graph: Linked Data


## Challenge 1: Idea management tools are rigid in capture medium

    The capture of an idea is often defined by the tool, and designers therefore find ideas to be distributed across several media and archives.
    
Idea Form
Vision: Dynamic Schema, Dynamic Levels of Detail, 

Dynamic Schema: RDF
Challenge: Dealing with inconsistencies in data "richness"

-> GI2MO tried an approach of unifying idea schemata

### Capturing and Identifying Ideas
Because designers use different tools for idea capture, they often have very distributed idea archives. Several designers described this as a challenge: “Do you ever go back and look at your old ideas? Why or why not?Not often enough, and that’s because they’re not necessarily filed properly for me to find them easily” (P13).

#### UUIDs

#### Versioning
Distributed System: Versioning very hard
Even harder for collaboration?

See Below

### How much structure is enough?
One of the oldest questions in computer science
RDF vs RDFS vs OWL, Clojure Spec, dynamic vs static typing

### Capturing Multimedia
Biggest Issue: multimedia
Capturing Aspekts, Facts about the Idea: RDF -> Defines What is stored, Limited set of how its stored, Transfer via encoding (xml, json-ld,etc)

With media:
Who stores it? What is stored? How is it transferred? How is it versioned?

### Transfer
Bridging the Gap between digital and analog (embodiment)

Getting from ad-hoc capturing tools to digitally usable media:
 - Audio Recordings: Voice Recognition
    (having ideas while walking -> embodiment)
 - photos of whiteboards
 - Post-It notes (clustering -> embodiment)
 - Sketchbook
 - Different Capturing "apps":
    - camera
    - recorder
    - scribble tool
    
#### Referencing External Data

Possibly Interesting Article:

https://medium.com/@mark..lee/realizing-ada-lovelaces-dream-of-human-machine-symbiosis-with-b43fb94d04c5

Interesting Fields:
Versioning, Collaboration, 
### Idea Archives
Re-finding ideas:
-> Metadata
-> Tags / Annotations
-> Classification: Topics / Keywords

"I would love that intelligent interface to file my documents and thoughts without me having to think about it, so it’d be based on the content in there or the type of idea that I’m coming up with.” 

### Opportunity Table
Support different modalities of capture and annotation and allow for saving to a shared idea database. Almost all designers described the challenge of their widely distributed idea archives. A consolidated archive from different tools would allow for designers to capture in the appropriate medium while not having to retrieve ideas from several locations.

Build systems to tag ideas easier with other context indicators than words: time, place, temporal context, people involved in project, quality of idea etc. Designers currently utilize makeshift signifiers to themselves, such as an arrow in the document title or documents in different colours to achieve different (visual) forms of tagging. Alternative modes of tagging ideas would provide cues for bringing ideas up again in relevant future situations, as well as additional cues for retrieving ideas.


## Challenge 2: Idea management tools offer inflexible interface and representations

     Idea management tool interfaces often support only one way of representing ideas; this hinders flexible work with ideas that requires shifting between and combining different representations.
     
Idea Representation

Most often, the interface a tool is chronologically ordered with no other structure

Most tools represent single files in their entirety and not parts of files or context of files.


Give the designers the possibility to define how an idea is displayed


The popularity of email as an idea management tool does not correspond with a general preference for visual tools. All designers we interviewed said they prefer extensively visual tools for managing their ideas when we asked them to imagine ideal tools. Email offers something particularly desirable to outweigh its limitations, namely that it is omnipresent and a natural part of the workflow


"Mood boards" -> Article Information Based Ideation

Clustering


### Opportunity Table
Allow for different views of ideas or files within tools, as well as maneuverability of files in relation to each other. Several designers highlighted the advantages of a large touchscreen that let them view many different files at once, as well as move them around. More flexible interfaces might encourage new clustering of files and lead to new discoveries and possibilities.

Allow for different types of highlights of different types of files. Several designers mentioned the challenge of annotating different types of files. Letting the designer tag or mark part of an image of a whiteboard and a corresponding video file would allow the designer to highlight particularly interesting parts of a shared idea process.


## Challenge 3: Idea management tools focus mainly on ideas, not ideation

    Most designers we spoke to were not looking for “yet another app” to help them brainstorm, but they were interested in tools that would help them develop their ideas. 

A key activity for designers is the process of developing ideas.

In my opinion: Out of scope for RDF / Knowledge bases. But: General-Knowledge Bases provide the "ambient knowledge" for decision making systems supporting the whole process:
 - Shepherding
 - Increasing the level of abstraction
 - Personalized Inspirations

### Inspiraton / Iteration / Reflection
Especially for handwritten notes and sketches, adding tags and annotation is experienced as difficult. While most digital idea capture tools offer a way to add tags or notes to individual files, most designers do not take the time to do so at the point of capture. Consequently, randomness can become the determining factor for whether the idea is ever revisited

While they aid the designer in the creation and overview of files, they do 
1322not actively help the designer reflect.

Approach: Show ideas that are thematically related to the problems the designer is currently thinking about

Challenge: Expressing "beneficial" rules for designers, that define what/when/how to show materials

#### Versioning
Inspiration from Github: Fork/Join/Commits
(Technical Side: Content Hashing)

Inspiration from Clojure: Persistent Data Structures

### Collaboration

Ideation Processes are heterogeneous: Nice literature about it: TODO paper integrating design thingy, litreview creativity support tools


Link to: Global Knowledge: How can computers help in ideation pipelines?

### Opportunity Table
Support the gap between capture and refining of ideas. A generalfinding was that idea management tools do not actively help the designer revisit their ideas or to translate them into actual design project. One way of doing this might be to allow the designer to mark ideas that they would like to get back to, and offerrevisiting of the idea, for instance by push-notifications or encouraging the move from note into a sketch and sketch into wireframe.

Help the designer reflect-in-action. Almost all design theory promotes the idea of the designer as a reflective practitioner, but despite this, few designers practice reflective thinking in a systematic way. Idea management tools might help the designer reflect on their own work by to encouraging the designer to answer short questions about their ideas or ask them to cluster their ideas in new patterns.

## Summary
Data and Metadata
-> Data and Code

Process and Product

Questions:
-> How to deal with the distributed system of idea management
-> How to generally encode process?
-> How to encode & manage binary-data
