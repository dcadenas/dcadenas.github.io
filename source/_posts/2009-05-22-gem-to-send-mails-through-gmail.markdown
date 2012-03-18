---
layout: post
title: "Gem to send mails through Gmail"
date: 2009-05-22T19:23:00-03:00
categories:
 - Ruby
comments: true
---
I made this little gem, `gmail_sender` that I find useful to log things when I'm running some script in my VPS, I use it for things like this:

```ruby
g = GmailSender.new("gmail_account", "password")
begin
  #Some interesting script that returns some interesting results in script_results
  g.send("dcadenas@gmail.com", "It worked!", script_results.to_yaml)
rescue => e
  g.send("dcadenas@gmail.com", "It didn't work :(", "#{e.message}\n#{e.backtrace}")
  raise e
end
```

So all you need to pass to the `send` method is an email address, the subject and the email content.

The source code is [here](http://github.com/dcadenas/gmail_sender/tree/master).
