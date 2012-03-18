---
layout: post
title: "Internet Explorer 7 accept header and Rails respond_to"
date: 2008-10-07T20:00:00-02:00
---
If you browse through IE to an url that should spit html but instead you see the feed reader page (the one with the text "You are viewing a feed that contains frequently updated content") then just be sure that the page's `respond_to` has the html mime type as its first item instead of `atom` or `rss`.

This solution addresses the way IE constructs its http request accept header which accepts any MIME type you may be serving so the first one available will be accepted which is not necessarily the html you are expecting.

Firefox doesn't have this problem because it explicitly states what it wants.
So in summary, change this:

```ruby
respond_to do |format|
  format.atom
  format.html
end
```

to this:

```ruby
respond_to do |format|
  format.html
  format.atom
end
```
