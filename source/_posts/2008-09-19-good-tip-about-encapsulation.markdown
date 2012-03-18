---
layout: post
title: "Tip about encapsulation"
date: 2008-09-19T18:46:00-03:00
categories:
 - Design
---
I was reading and [article](http://www.martinfowler.com/bliki/GetterEradicator.html) about encapsulation on Martin Fowler's blog when I found this simple and practical tip:

{% blockquote Kent Beck http://www.martinfowler.com/bliki/GetterEradicator.html %}
Always beware of cases where some code invokes more than one method on the same object
{% endblockquote %}

It's not a rule but I think it can be considered one more code smell to keep in mind.
