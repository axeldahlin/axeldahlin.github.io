---
title: "Amend old commit"
date: 2019-07-19T14:01:25+02:00
draft: false
categories: git
tags: git
permalink: /:categories/:title
layout: post
---

Copy the commit hash of the commit *before* the one you want to edit. 

```
git rebase --interactive 8869g7a6e0
```

In the editor, change pick to edit on your commit.

Make your changes and continue by doing:

```
git commit --all --amend --no-edit
```

```
$ git rebase --continue
```




