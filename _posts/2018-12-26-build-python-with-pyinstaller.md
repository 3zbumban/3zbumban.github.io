---
layout: post
title: "Build python with pyinstaller"
comments: true
description: "Build python with pyinstaller"
keywords: "Build python pyinstaller"
---

# Build python scripts (.py) with [pyinstaller](https://www.pyinstaller.org/)

## Install [pyinstaller](https://www.pyinstaller.org/)

```sh
pip install pyinstaller
```

## Build you programm

```sh
pyinstaller --onefile app.py
```

### Description

- `--onefile`  used to package everything into a single executable. If you do not specify this    option, the libraries, etc. will be distributed as separate files alongside the main            executable.

- `--windowed` prevents a console window from being displayed when the application is run. If you're releasing a non-graphical application (i.e. a console application), you do not need to use this option.

- `app.py` the main source file of the application. The basename of this script will be used to name of the executable, _however you may specify an alternative executable name using the `--name` option._

#### Adding an icon

- `--icon=app.ico`