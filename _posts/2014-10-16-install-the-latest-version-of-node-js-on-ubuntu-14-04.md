---
layout: post
title: Install the latest version of Node.js on Ubuntu 14.04
date: 2014-10-16 12:49:48.000000000 -04:00
categories:
- open-source
tags:
- open-source
status: publish
type: post
published: true
meta:
  _wpas_skip_facebook: '1'
  _wpas_skip_google_plus: '1'
  _wpas_skip_twitter: '1'
  _wpas_skip_linkedin: '1'
  _wpas_skip_tumblr: '1'
  _wpas_skip_path: '1'
  _publicize_pending: '1'
  _rest_api_published: '1'
  _rest_api_client_id: "-1"
---

Since I am using [Elementary OS](http://elementaryos.org/) (Freya, based on Ubuntu 14.04) on my laptop, the Node.js version in repository is a bit old.  When I tried setting up [Makedrive](https://github.com/mozilla/makedrive), I got something like this:

{% highlight bash %}
 sh: 1: node_modules/.bin/bower: not found
 npm WARN This failure might be due to the  use of legacy binary "node"
 npm WARN For further explanations, please read /usr/share/doc/nodejs/README.Debian
{% endhighlight %}

It's kinda weird that it said "not found" while the file actually exists, but usually it is related to binary incompatibilities .  In order to fix it, we need to add a [NodeSource](https://nodesource.com/) repository:

{% highlight bash %}
curl -sL https://deb.nodesource.com/setup | sudo bash -
{% endhighlight %}

Then install Node.js:

{% highlight bash %}
sudo apt-get install -y nodejs
{% endhighlight %}

Enjoy!

Source: [Offical guide on github](https://github.com/joyent/node/wiki/installing-node.js-via-package-manager)
