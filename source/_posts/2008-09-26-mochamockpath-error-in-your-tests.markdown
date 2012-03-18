---
layout: post
title: "mocha_mock_path error in your tests"
date: 2008-09-26T12:29:00-03:00
categories:
 - Testing
 - Ruby
 - mocha
---
If you use stubs in your Mocha tests but they break because of this error:

```
ActionView::TemplateError: undefined method `mocha_mock_path'
```

Check that you also stub the `class` method.

```ruby
stub(:title => 'a title', :class => News)
```
