---
layout: post
title: "Architects and programmers"
date: 2007-11-09T19:48:00-02:00
categories:
 - Design
---
I'm currently working in a project for a client bank. Some days ago we had a meeting where they showed us their IT's organizational chart which had been recently updated. They had two departments, one of them was made by business analysts and software architects, and the other department is the software factory where programmers are supposed to be. I interpreted that they were even physically two different sections. I'm not sure if I'm alone in this but I think this separation is wrong. I think that architects belong to the same space as developers because they are essentially the same thing.

Architects are programmers
--------------------------

We should notice that architecture is a subset of design which implies that an architect is a designer. Now, if we agree that [programmers are the designers of software](http://www.developerdotstar.com/mag/articles/reeves_design_main.html) then a good programmer that is capable of designing this subset, is an architect. Also notice that there are no good architects that are bad programmers. Being a good programmer is a prerequisite for being an architect.

{% img center /images/arch.gif %}

So a programming language is not more nor less than a software design language.
Of course there are other tools to design software (diagrams, etc), but a programming language is better as its product is the only design representation that is directly interpreted by the computer and the only one that has a 1 on 1 relation between what you expect and what you get.
Used correctly, they are better at communicating a design than the alternatives.

So architects should program but they also should do it in the same physical space as the rest of programmers. Not only because they have to communicate their ideas but also for two extra benefits:

* Feedback.
  Probably the most essential characteristic of software design is that it evolves by iterating. Even when doing waterfall, you evolve and iterate (the problem is that you stop too early doing so and you do it on paper). This evolution can only be done with realtime feedback and you won't get feedback if you are not inspecting and touching the guts of your child.
  You can only assess the correctness of your initial "paper level architecture" with the detailed "code level architecture", you should have a deep understanding of the most real representation of your architecture so you can be able to gather immediate feedback both against interpretation errors when some developer didn't understand you and against your own errors. Even if you are errorless (I don't believe that), feedback lets you learn about the domain and improve continuously your design.

* Maximizing transfer of expertise and knowledge.
  If an architect is just a good and respected developer, then why not transfer its merits to the teammates. This would end up being a win-win situation because they'll keep improving and they know they will be responsible for the general improvement. The waste and problems that represent using programmers as if they were code generation tools is as silly as having not programming architects. Their design abilities must be improved. If they can't improve, well, then they are too stupid and risky even as a code generation tool, so don't hire them if you don't intend to use them as architects.

The separation problem
----------------------

Divide and conquer it's a great heuristic. But if you fail to spot the point in which you should stop dividing, then it's counterproductive. Some things belong together. And when those things are split you'll find problems.
So if we have an architect that is not involved in programming we'll get two situations:

* We have an good programmer, maybe the best in our company, that is being used only for writing word documents and making presentations and diagrams. This is any design representation you imagine except the one in which he is good at and at the same time the one that is the more important and cannot be skipped. Yes, this is the one that is least understood by other departments of the company, but the architect role should be constructing software, his main target of communication are the programmers from the trenches. Communication with the rest is secondary.

* We have a bad programmer that was choosen for some reason to make the architecture of the system. Let's not extend on this for obvious reasons.
