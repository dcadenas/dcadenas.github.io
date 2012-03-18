---
layout: post
title: "Reverse Ajax and Prototype with Mongrel handlers"
date: 2008-08-25T23:38:00-03:00
categories:
 - javascript
 - reverse ajax
 - comet
 - Ruby
 - mongrel
 - ajax
 - prototype
comments: true
---
A common use of [reverse Ajax or Comet](http://en.wikipedia.org/wiki/Reverse_Ajax) calls is having some piece of information in your webpage that you want to update as soon as some remote event triggers, always without polling. Let's make a little experiment to see how this works:

Client side
-----------

So you start a request, the web server waits for the event to happen, and finally, a while later, the response is sent back to the client. When this process ends, it's very common that you want to start it again. You want to have a continuous ajax call when the event is also continuous, when it can happen many times.
To deal with this, as I'm using [prototype](http://www.prototypejs.org/), I made this javascript routine to start listening for the event:

```javascript
function continuousAjaxCall(url, method, params, successCallback){
  waitingForResponse = false;
  function iteration(){
    if(!waitingForResponse){
      waitingForResponse = true;
      new Ajax.Request(url, 
       {
         method: method,
         parameters: params,
         onSuccess: theSuccessCallback
       });
    }
  };

  function theSuccessCallback(transport){
   successCallback(transport.responseText);
   waitingForResponse = false;
  };
  
  return new PeriodicalExecuter(iteration, 1);
} 
```

So now if you do:

```javascript
continuousAjaxCall("/WebFacade/SomeWebService", "post", "taskid=" + taskNumber, callback);
```

you will start listening to the web service in `/WebFacade/SomeWebService` using method post and with `taskid=taskNumber` as the http body parameter.
The callback is a routine that will be executed each time the event is triggered. For example we could do this to show the result from the web service:

```javascript
function callback(responseText)
{
  alert(responseText);
}
```

The routine returns a prototype [`PeriodicalExecuter`](http://www.prototypejs.org/api/periodicalExecuter) that you can use to stop listening:

```javascript
pe = continuousAjaxCall(...
pe.stop()
```

Server side
-----------

In the server side I have some [Mongrel handlers](/blog/2008/08/24/standalone-mongrel-handler-hello-world) serving the client pages. The key here is the line sleep 1 until `@@submitted_value` that waits until some new value is submitted and **only** then responds to the ajax request:

```ruby
require 'rubygems'
require 'mongrel'
include Mongrel

@@submitted_value = nil

class ReverseAjaxHandler < HttpHandler
  def process(request, response)
    response.start(200) do |head,out|
      head['content-type'] = 'text/html'
      sleep 1 until @@submitted_value
      out << @@submitted_value
      @@submitted_value = nil
    end
  end
end

class SendHandler < HttpHandler
  def process(request, response)
    response.start(200) do |head,out|
      #Code that renders the "/send" page and sets the @@submitted_value
      #...  
      #...  
    end
  end
end

h = HttpServer.new("0.0.0.0", "5000")
h.register("/wait", ReverseAjaxHandler.new)
h.register("/send", SendHandler.new)
h.register("/files", DirHandler.new('.'))
h.run.join
```

It's nice to have this as a Mongrel handler because it's simple, but keep in mind that this implementation was made just for the purpose of this example and it is not thread safe. I don't control the access to the global variable `@@submitted_value`.

The code for this article can be found [here](http://dcadenas.googlepages.com/ReverseAjaxExperiment.zip).
