---
layout: post
title: "More about refactoring"
date: 2007-12-08T19:09:00-02:00
categories:
 - Refactoring
 - Design
comments: true
---
Some points of disagreement with the critique against the [refactoring book](http://www.amazon.com/Refactoring-Improving-Existing-Addison-Wesley-Technology/dp/0201485672) found in [this article about smells](http://www.codinghorror.com/blog/archives/000589.html).

  * Assuming that he is right in that most of us know how to refactor, I think that's because experience gave us the needed knowledge. Time and pain was needed. This time and pain, as in any knowledge area, can be reduced by reading books, like Fowler's.

  * Apart from this, I think even a developer with experience and knowledge of most refactorings could miss some smells. We are humans and we acquire bad habits.

  * A big part of the knowledge gained with experience is too intuitive and that brings some problems. When things are intuitive and you suddenly find someone that doesn't share your intuition you have to discuss with solid explicit arguments. Fowler's book helps you ease the work needed to find those arguments letting you show clearly why your intuition is the way it is. You can do it yourself of course, but it's easier to reuse the effort someone else did, if you share it of course.

  * The book defines a vocabulary to deal with our intuition or implicit concepts, that is very very important. Now we can share it and we can communicate more efficiently. The same advantage we discovered after design patterns appeared.

  * He agrees with Fowler that smells are important. The book is a reference to smells. IMO refactoring is more about identifying design problems (smells) than about the relatively simple things needed to make them disappear, but it's both.

  * Things that are important, like smells, must be made explicit so the problem can be easily studied and possibly build some more knowledge on higher level concepts. One of those higher level concepts that could be further developed was the development philosophy of [Continuous Design](http://martinfowler.com/ieeeSoftware/continuousDesign.pdf) in which a core concept is refactoring.

  * I think there's a confusion between simplicity and importance. Not only complicated books are important.

Seems that a big reason for this disagreement comes from not seeing a tight relationship between code smells and refactoring as explained in [this previous post](/blog/2007/12/03/meaning-of-refactoring).
