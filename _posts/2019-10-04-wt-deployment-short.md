---
layout: post
title: "WT-Deployment short"
comments: true
description: "wt deploymenet short version"
keywords: "wt deployment now.sh heroku mlab"
---

# Deployment

## database on [mlab](https://mlab.com/)

1. create [mlab](https://mlab.com) account
2. create new database
3. create a databse user
4. retrieve uri and user from mlab

## server with [heroku](https://www.heroku.com/)

`https://git.heroku.com/wt-test-projekt.git`
0. set mongodb uri in `src/config/config.js`

1. kostenlosen account bei [heroku.com](https://www.heroku.com/)
2. [heroku cli installieren](https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up)
3. mit cli einloggen `heroku login`
4. heroku projekt anlegen online oder cli: `heroku create <...>`
5. heroku als remote hinzufügen `heroku git:remote -a <...>`
6. server folder zu heroku pushen `git subtree push --prefix server heroku master` (server ist der zu pushende subfolder)-> [SO](https://stackoverflow.com/a/10648623/9588092)
   (oder `npm run deploy`)

### => [docs](https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up)

## [client with now](https://cli.vuejs.org/guide/deployment.html#now)

1. set api url in `src/config/config.js` to heroku api url
2. kostenlosen account bei [now.sh](https://zeit.co/) anlegen
3. `npm install -g now`
4. settings sind in `now.json`
5. *`npm run deploy`* (`npm run build && now --public && now alias`)

### => [Docs](https://cli.vuejs.org/guide/deployment.html#now)
