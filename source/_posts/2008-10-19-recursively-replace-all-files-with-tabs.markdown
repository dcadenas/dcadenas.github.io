---
layout: post
title: "Recursively replace all files with tabs in Linux"
date: 2008-10-19T23:58:00-02:00
categories:
 - linux
---
Ok I don't want to forget this ever again so I will write it here.

```bash
sed 's/  //g' `find -type f`
```

**Note:** I'm using both the grave accent ``` ` ``` and the apostrophe `'`. ``` ` ``` is used to create a special kind of shell escape that substitutes each line of the output in the place you inserted it. So sed will be called once for each file found by find.

It's the same as doing manually:

```bash
sed 's/  //g' ./file1.txt
sed 's/  //g' ./file2.txt
sed 's/  //g' ./dir/file2.txt
```

To type the tab inside the sed regexp hit ctrl-v and then the tab key.
`find -type f` will show in each line the path of each file recursively.
