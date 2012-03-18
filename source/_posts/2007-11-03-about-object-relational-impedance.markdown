---
layout: post
title: "About the object-relational impedance mismatch"
date: 2007-11-03T00:52:00-02:00
categories:
 - Design
 - DDD
---
I agree 100% with [this Bob Martin's post](http://blog.objectmentor.com/articles/2007/11/02/active-record-vs-objects) about the problems that arise when using the Active Record data layer pattern.

I think Active Record's problems come from implementing it from the beginning of your project which has the risk of biasing your design towards a weak domain model. You will tend to make design decisions that fit well with Active Record and it will be more difficult to realize you should be refactoring towards having a domain model.

You can't be sure whether your app will be really data-centric until it's finished and the most flexible design to cope with this doubt is **starting** with the **simplest** domain model. If at the end it gets anemic and you don't find it's behaviour outside, possibly in a service layer, then you can substitute it with the data layer, which could be Active Record.

So I like Martin's idea of considering the datalayer as an implementation detail. It may be an important detail, but details don't belong to abstractions, and if you mix them you fix'em (sorry couldn't avoid that).

It's easier to start flexible and then tighten than start tight and then get flexible. So I think it's easier to add Active Records to your domain models than adding a domain model to your Active Records. And you'll have the advantage that you are not tied with a particular Active Record implementation.

I'd use a pure AR solution only if I'm very very sure that I'm dealing with a simple CRUD that won't change in the future, and even then I'd feel uncomfortable. The application may be data centric now but you can't be sure if it will keep being that way in the future. You don't know that even if you are the only client of the app.
