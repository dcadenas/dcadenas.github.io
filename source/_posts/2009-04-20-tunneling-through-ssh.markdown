---
layout: post
title: "Tunneling through SSH"
date: 2009-04-20T17:45:00-03:00
categories:
 - sysadmin
comments: true
---
To tunnel through ssh do:
```bash
ssh -v -nNT4 -R :4007:localhost:3000 myhost
```
which maps the remote port 4007 to the local port 3000.
`myhost` is the host you want to connect and it's a good idea to have it as an entry in your ssh config.
