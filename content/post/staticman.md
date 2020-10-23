---
title: Staticman
author: Iacopo Moles
date: 2020-10-22T23:22:07.833+00:00
tags:
- tutorial
- comments
latex: false
toc: false
banner: ''

---
How to setup your comments

<!--more-->

## Generating Private Access Token

Head to Github and on Settings -> Developer Settings -> Personale Access Tokens and click [Generate New Token](https://github.com/settings/tokens/new).

Write a placeholder name and select the repo and user subsections. Then press Generate token.

Copy the new token generated and save it somewhere. Keep in mind that you can't recover it in future.

## Deploy on Heroku

Head over to the GitHub [project page](https://github.com/eduardoboucas/staticman/) and click the purple button (or in alternative [click here](https://dashboard.heroku.com/new?button-url=https%3A%2F%2Fgithub.com%2Feduardoboucas%2Fstaticman&template=https%3A%2F%2Fgithub.com%2Feduardoboucas%2Fstaticman)).

You will land on a page where a name for your project is asked. Type whatever name you would like and confirm.

At the end of the setup you can continue on Manage App.

## Generate Private Key

From the toolbar click More -> Run Console and type `openssl genrsa -out key.pem && cat key.pem` and then press Save Session. 

A .txt file is going to be downloaded. Open it and copy the section made by:

```conf
-----BEGIN RSA PRIVATE KEY-----
(a long alphanumerical text)
-----END RSA PRIVATE KEY-----
```

You will need it later.


## Configure the environment variables

Go to Settings -> Config Vars and type the following fields:

`NODE_ENV` = `production`

`GITHUB_TOKEN` = [(Private Access Token from before)](#Deploy-on-Heroku)

`RSA_PRIVATE_KEY` = [(Private Key from before)](#Generate-Private-Key)

