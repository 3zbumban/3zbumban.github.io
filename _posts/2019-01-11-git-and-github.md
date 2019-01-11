---
layout: post
title: "git & gihub"
comments: true
description: "git and github routines"
keywords: "git github cheatsheet"
---

# Git and Github

## basics

```sh
git status
git log

git add <your files to add>
git commit -m "your commit message"

git push
git pull
```

## configuration

```sh
git config --list
```

```sh
git config user.name "your name"
```

```sh
git config user.email "your_email@example.com"
```

## add current local projekt to existing github repo

```sh
git init
git add .
git commit -m "my commit"

git remote add origin <remote repository URL>

git push origin master
```

## overwrite local repository with a remtote one

```sh
git fetch origin
git reset --hard origin/master
```