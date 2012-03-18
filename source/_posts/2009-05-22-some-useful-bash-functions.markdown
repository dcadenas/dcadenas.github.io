---
layout: post
title: "Some useful bash functions"
date: 2009-05-22T19:12:00-03:00
categories:
 - vim
---
I use this bash functions to open vim with splits for each file in which grep or rak find the pattern I'm searching for:
```bash
grepvim(){
  grep -rl "$1" $2| xargs mvim -o +/"$1"
}

rakvim(){
  rak -l "$1" $2| xargs mvim -o +/"$1"
}
```
