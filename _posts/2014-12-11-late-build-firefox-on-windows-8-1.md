---
layout: post
title: "[Late] Build Firefox on Windows 8.1"
date: 2014-12-11 01:24:24.000000000 -05:00
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
To Build firefox on Windows 8.1, there are a few steps needed.

1. Install Visual Studio (2010 - 2013)
2. Download and install mozilla-build bundle
3. Runs start-shell-msvc2013.bat in C:\mozilla-build and It will give you a CLI environment for compilation using Visual Studio 2013.
4. Cd to the root of the source folder that is downloaded from Mozilla repository

Build it by running:

{% highlight bash %}
./mach build
{% endhighlight %}

Finally, Runs it:

{% highlight bash %}
./mach run
{% endhighlight %}

Thanks to Mozilla, the whole building process is pretty smooth without any configurations. :)

![Alt screenshot1](https://gklo.files.wordpress.com/2014/12/ff1.png)

![Alt screenshot2](https://gklo.files.wordpress.com/2014/12/ff2.png)

![Alt screenshot3](https://gklo.files.wordpress.com/2014/12/ff3.png)

Done!
