---
layout: post
title: "One thing to keep in mind when extending Ruby classes"
date: 2008-10-06T02:07:00-02:00
categories:
 - Ruby
comments: true
---
I was reading this [post](http://eigenclass.org/hiki/class+hierarchy+introspection+evil.rb) in Mauricio Fernandez's blog (rcov) and I got surprised about the behavior I'm summarizing in the following code:

```ruby
class A
  def foo
    "A#foo"
  end
  
  def singleton_class
    class << self
      self
    end
  end
end

a = A.new
puts a.foo #=> A#foo
puts a.singleton_class.ancestors.inspect #=> [A, Object, Kernel]

module X
  def foo
    "X#foo"
  end
end

class A
  include X
end

a.extend X
puts a.foo #=> A#foo (and not X#foo!!!!!!!)
puts a.singleton_class.ancestors.inspect #=> [A, X, Object, Kernel] (and not [X, A, X, Object, Kernel])
```

So remember, you cannot extend or include a class with a module that is already present in the ancestors chain, it will be ignored!
