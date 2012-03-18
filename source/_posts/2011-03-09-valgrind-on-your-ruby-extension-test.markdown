---
layout: post
title: "Valgrind on your ruby extension test"
date: 2011-03-09T21:47:00-02:00
categories:
 - Ruby
comments: true
---
```bash
valgrind --num-callers=50 --error-limit=no --partial-loads-ok=yes --undef-value-errors=no rspec spec/extension_spec.rb
```
