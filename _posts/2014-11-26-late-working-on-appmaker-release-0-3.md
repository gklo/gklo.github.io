---
layout: post
title: "[Late] Working on appmaker (Release 0.3)"
date: 2014-11-26 00:43:47.000000000 -05:00
categories:
- open source
tags:
- open source
status: publish
type: post
published: true
meta:
  _wpas_skip_google_plus: '1'
  _wpas_skip_facebook: '1'
  _wpas_skip_twitter: '1'
  _wpas_skip_linkedin: '1'
  _wpas_skip_tumblr: '1'
  _wpas_skip_path: '1'
  _publicize_pending: '1'
  _rest_api_published: '1'
  _rest_api_client_id: "-1"
---
For Release 0.3, in order to have different experience, I chose a bigger project to work on - Appmaker.

##Pull request

<https://github.com/mozilla-appmaker/appmaker/pull/2370>  
<https://github.com/mozilla-appmaker/appmaker/pull/2371>

##Previous pull request for 0.2 (since I forgot put the link into 0.2 blog post)

<https://github.com/mozillafordevelopment/webmaker-app/pull/386>  

<br/>The first problem I encounter is an error about "loginHost for webmaker-auth":

```bash
Warning: PUBLISH_HOST is unset. See README.md for more info.
Warning: ASSET_HOST is unset. See README.md for more info.

/home/rickdom/seneca/osd600/appmaker/node_modules/webmaker-auth/index.js:14
 throw new Error('(webmaker-auth): secretKey was not passed into webmaker-a
 ^
Error: (webmaker-auth): secretKey was not passed into webmaker-auth
 at new module.exports (/home/rickdom/seneca/osd600/appmaker/node_modules/webmaker-auth/index.js:14:11)
 at Object.&lt;anonymous&gt; (/home/rickdom/seneca/osd600/appmaker/app.js:81:20)
 at Module._compile (module.js:456:26)
 at Object.Module._extensions..js (module.js:474:10)
 at Module.load (module.js:356:32)
 at Function.Module._load (module.js:312:12)
 at Function.Module.runMain (module.js:497:10)
 at startup (node.js:119:16)
 at node.js:906:3
```

However, this took me a whole week to figure out how to fix the problem... End up the reason I got this because I forgot to do one step:

```bash
cp sample.env .env
```

Really, it is too important to follow every single step in README.md, especially for big project.  

<br/>In this release. I also found a really easier way to search for elements on the page.  When I want to get the code that handles the close button on tab, I can simply search for the title/alt, "Delete this card", to get the file that contains the code.
