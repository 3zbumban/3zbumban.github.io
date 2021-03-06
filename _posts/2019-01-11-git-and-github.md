---
layout: post
title: "git & github"
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

``` sh
git remote -v
```

## configuration

```sh
git config --list
```

```sh
git config user.name "your name"
git config --global user.name "your name"
```

```sh
git config user.email "your_email@example.com"
git config --global user.email "your_email@example.com"
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

### errors

#### 'fatal: refusing to merge unrelated histories'

*fix:* add the `--allow-unrelated-histories` flag

```sh
git pull origin master --allow-unrelated-histories
```

-> [SO entry](https://stackoverflow.com/a/53663271/9588092)