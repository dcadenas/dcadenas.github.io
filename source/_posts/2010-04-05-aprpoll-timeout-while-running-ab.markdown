---
layout: post
title: "apr_poll timeout while running ab"
date: 2010-04-05T02:40:00-03:00
categories:
 - sysadmin
comments: true
---
If you get this error while running `ab` (ApacheBench) on your mac:

```
apr_poll: The timeout specified has expired (70007)
```

It may get fixed with:

```bash
sudo sysctl -w net.inet.ip.portrange.first=32768
sudo sysctl -w net.inet.tcp.msl=100
```
