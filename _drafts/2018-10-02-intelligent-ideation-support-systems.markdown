---
layout: post
title:  "Intelligent Ideation Support Systems"
date:   2018-07-13 10:00:00 +0200
categories: collaborative-ideation
---

# Motivation
In order to support people in brainstorming tasks, we first need to understand the cognitive processes happening, at least on a heuristic level.
Understanding different strategies of how people come up with new ideas based on their surroundings, perception and experiences could lead to detecting and actively encouraging the currently selected problem solving strategy or proactively triggering a strategy change when the current one fails.

//TODO example

Psychology has proposed one model of cognitive processes during ideation that is particularly interesting: The "Search for Ideas in Associative Memory" Model ([Nijstad, B. A., & Stroebe, W. (2006)](http://journals.sagepub.com/doi/abs/10.1207/s15327957pspr1003_1)). This model describes the idea generation process as activations of "images" in the Long Term Memory (LTM) that are subsequently used as an input to generate ideas.
This model has been validated and used by research in the collaborative-ideation field, for example in "Semantically Far Inspirations Considered Harmful?" ([Chan et al (2017](https://dl.acm.org/citation.cfm?id=3059455)). One drawback of the aforementioned paper, is that it talks about ideas only (not the images mentioned in the SIAM paper). Ideas are compared using LSA and then SIAM is used as a motivation to display "near" (LSA similar) idea exemplars during productive ideation and "far" (LSA dissimilar) exemplars during impasses.
My hypothesis is that we can represent these images by means of semantic concepts, extracted from the idea texts.
In our [last publication](https://dl.acm.org/citation.cfm?id=3188485), we asked amazon mechanical turk workers to generate ideas for a new technology, validate the concepts they used and tracked the timings of the idea submissions and inspiration requests (link).
If the extracted concepts used in ideas are an accurate representation of images in the SIAM sense, we should see the following things in the ideas generated in one session:
 - Foo
 - Bar
 - Baz
 
The question now becomes: Can we actually model the cognitive processes during ideation based on the data we have (namely: timings of idea submissions and concepts used)?
In my naive imagination, we could actually predict concepts with a statistical propability, based on the concepts used by the user so far. If a user has three ideas that mention "car", what is the likelihood of their fourth idea having "car" in it?

//TODO figure

# Machine Learning to the rescue?
TODO: advantages/drawbacks

# Resources
 - Chan, Joel, et al. "Semantically Far Inspirations Considered Harmful?: Accounting for Cognitive States in Collaborative Ideation." Proceedings of the 2017 ACM SIGCHI Conference on Creativity and Cognition. ACM, 2017.
 - Nijstad, Bernard A., and Wolfgang Stroebe. "How the group affects the mind: A cognitive model of idea generation in groups." Personality and social psychology review 10.3 (2006): 186-213.
 - Wang, Kai, Jeffrey Nickerson, and Yasuaki Sakamoto. "Crowdsourced idea generation: The effect of exposure to an original idea." Creativity and Innovation Management 27.2 (2018): 196-208.
 - Mackeprang, Maximilian, Abderrahmane Khiat, and Claudia Müller-Birn. "Concept Validation during Collaborative Ideation and Its Effect on Ideation Outcome." Extended Abstracts of the 2018 CHI Conference on Human Factors in Computing Systems. ACM, 2018. 

