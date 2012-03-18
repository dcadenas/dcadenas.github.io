---
layout: post
title: "Singleton class magic without using singleton classes"
date: 2008-09-03T11:25:00-03:00
categories:
 - Metaprogramming
 - Ruby
comments: true
---
Excellent posts [here](http://blog.jayfields.com/2008/04/extend-modules-instead-of-defining.html) and [here](http://blog.jayfields.com/2008/07/ruby-underuse-of-modules.html) by Jay Fields where he gives an alternative to use singleton classes.

Instead of doing this:

```ruby
class << self
  def hi
    puts 'Hi'
  end
end
```

he proposes to do this:

```ruby
mod = Module.new do
  def hi
    puts 'Hi'
  end
end
extend mod
```
