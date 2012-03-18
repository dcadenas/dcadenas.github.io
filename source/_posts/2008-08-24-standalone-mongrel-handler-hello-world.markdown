---
layout: post
title: "Standalone Mongrel handler Hello World"
date: 2008-08-24T14:00:00-03:00
categories:
 - mongrel
comments: true
---
I think this is the simplest Mongrel handler you can create. It doesn't depend on Rails so this is not what you need to write if you want to install a Rails friendly Mongrel handler.

```ruby
require 'rubygems'
require 'mongrel'

class HelloHandler < Mongrel::HttpHandler
  def process(request, response)
    response.start(200) do |head,out|
      out << 'Hello World!'
    end
  end
end
```

h = Mongrel::HttpServer.new("0.0.0.0", "5000")
h.register("/hello", HelloHandler.new)
h.run.join

**Notes:** If you want to output html remember to `include head['content-type'] = 'text/html'` inside the inner block.
To include static pages you can add `h.register("/files", DirHandler.new('.'))`. After this you can access all files in the current directory through `http://localhost:5000/files`.
