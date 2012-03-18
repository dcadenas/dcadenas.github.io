---
layout: post
title: "CORS with Ext.js"
date: 2011-10-11T19:04:00-02:00
categories:
 - javascript
comments: true
---
```javascript
Ext.Ajax.useDefaultXhrHeader = false
Ext.Ajax.request({url:'http://ipv4.0-9.fi', success: function(res,req){alert(res.responseText)}})
```
