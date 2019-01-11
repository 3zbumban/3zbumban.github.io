---
layout: post
title: "git & gihub"
comments: true
description: "git and github routines"
keywords: "git github cheatsheet"
---

# Git and Github

## add current local projekt to existing github repo

```sh
git init
git add .
git commit -m "my commit"

git remote set-url origin git@github.com:username/repo.git
git remote add origin <remote repository URL>

git push origin master
```

## overwrite local repository with a remtote one

```sh
git fetch origin
git reset --hard origin/master
```