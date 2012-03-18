---
layout: post
title: "The meaning of refactoring"
date: 2007-12-03T02:21:00-02:00
categories:
 - Refactoring
 - Design
---
For a lot of people refactoring is not important. For some people this is because they don't know the correct meaning. They think it's just the name someone made up to describe any code change.

That's not refactoring.

You refactor when the changes you make **improve** the design while keeping its behaviour unchanged. Knowing [when](http://martinfowler.com/bliki/CodeSmell.html) and [how](http://www.amazon.com/Refactoring-Improving-Existing-Addison-Wesley-Technology/dp/0201485672) this improvement should be systematically made is what is taught in the literature.

But there's another group of people that know the correct definition but still don't believe in it. This is because they measure their design quality just by its behaviour, so if the code already does what it's intended to do, they think it's good code. They believe in the *Don't touch the design if it's not broken* mantra (a slightly more valid reason to believe in this comes from lacking a good set of tests that act as a safety net for your design improvements).

For this reason they slowly start accumulating [design debt](http://c2.com/cgi/wiki?DesignDebt). At some point, not too far in time, this unattended design improvement brings the impossibility to change code as it can't be controlled. This is because it's too difficult to understand and see all consequences of any change they may do, so either they don't change code anymore, or if they do, they start seeing bugs appear everywhere because they broke something they couldn't see it could get broken. So they say *You see? I was right, code shouldn't be changed if it's not broken*, a self-fulfilling prophecy.

So in summary, refactoring requires the ability to systematically [identify](http://martinfowler.com/bliki/CodeSmell.html) and improve problematic designs and it's important because it pays your design debt. This is necessary to understand and change your code easily.

This are great books you can read to improve refactoring skills:

* [Refactoring: Improving the Design of Existing Code](http://www.amazon.com/Refactoring-Improving-Existing-Addison-Wesley-Technology/dp/0201485672)
* [Refactoring to Patterns](http://www.amazon.com/Refactoring-Patterns-Addison-Wesley-Signature-Kerievsky/dp/0321213351)
* [xUnit Test Patterns: Refactoring Test Code](http://www.amazon.com/xUnit-Test-Patterns-Refactoring-Addison-Wesley/dp/0131495054)
