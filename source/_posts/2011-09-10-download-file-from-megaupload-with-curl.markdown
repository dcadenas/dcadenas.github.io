---
layout: post
title: "Download a file from Wupload or Filesonic with curl"
date: 2011-09-10T16:42:00-03:00
categories:
 - sysadmin
comments: true
---
Wupload:
```bash
curl -d "email=your@email.com&password=yourpassword&redirect=/file/159344782" -b cookies.txt -c cookies.txt  www.wupload.com/account/login -L -o 20110910StokevsLiverpool1ertPachorriarte.mkv
```

Filesonic:
```bash
curl -d "email=your@email.com&password=yourpassword&redirect=/file/2820172905" -b cookies.txt -c cookies.txt www.filesonic.com/user/login -L -o somevideo.wmv
```
