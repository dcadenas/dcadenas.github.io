---
layout: post
title: "Capistrano and Git problems"
date: 2008-12-12T15:51:00-02:00
categories:
 - ssh
 - git
comments: true
---
If you get this error when deploying with Capistrano:

```
ERROR:gitosis.serve.main:Repository read access denied
```

You may solve it with:

```bash
ssh-add ~/.ssh/id_rsa
```

This is needed because my ssh config is configured to forward my identity to the deployment machine (with `ForwardAgent yes`) so the ssh agent must know my private key.
