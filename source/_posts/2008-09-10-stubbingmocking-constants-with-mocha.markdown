---
layout: post
title: "Stubbing/Mocking constants with Mocha"
date: 2008-09-10T12:34:00-03:00
categories:
 - BDD
 - Testing
 - Ruby
 - mocha
comments: true
---
As far as google told me, it seems you can't use Mocha against constants.

One alternative [proposed](http://rubyforge.org/pipermail/mocha-developer/2007-July/000394.html) is changing the constant in the test where you need it like these:

```ruby
class Module
   def redefine_const(name, value)
     __send__(:remove_const, name) if const_defined?(name)
     const_set(name, value)
   end
end
```

And inside the test case you change the constant to what you need and restore it after the test ends:

```ruby
Object.redefine_const(:RAILS_ENV, 'production')
```

But if you can control the code that uses the constant there's a more clean way. Just wrap it in a method and get the constant through the method. During testing you just mock the method:

```ruby
class A
  def rails_env
    RAILS_ENV
  end
  #...some more code that gets the constant RAILS_ENV using the method rails_env...
end
```

And then in your test you just do a normal expectation:

```ruby
A.any_instance.expects(:rails_env).returns 'production'
```

You could even have some module that wraps all useful constants in your app, so constant dependent code gets easily testable and clean.
