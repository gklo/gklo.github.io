---
layout: post
title: Experience of collaboration with Webmaker team (Release 0.2)
date: 2014-10-23 02:44:46.000000000 -04:00
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
<h3>Pull request (Updated on Nov 25)</h3>
<p><a href="https://github.com/mozillafordevelopment/webmaker-app/pull/386" target="_blank">https://github.com/mozillafordevelopment/webmaker-app/pull/386</a></p>
<h3>Picking a bug</h3>
<p>The first thing to do is picking a bug. It is a thing which is harder than I imagine. When I have no understanding about project details, I was quite confusing about which bug is proper for me to work on. Dave did teach us to pick something with “first bug” tag. However, most of the first bugs were picked already because I started doing it quite lately.</p>
<h3>The projects</h3>
<p>In order to pick a proper bug, I started to try out some of the project, like Webmaker Mobile, Appmaker, and MakeDrive. It still took me a day to set up the environment because there were some error or issue when I built certain project. As I fixed more issues, I found myself more comfortable with tools like bower, gulp, npm. It was such a great chance for me to understand more about them really quickly. After trying out each of the projects, I ended up taking Webmaker Mobile for my assignment. It is because either MakeDrive or filer are low-level libraries which is more difficult to understand. On the other side, appmaker is having large size of files compared to Webmaker. Finally, I picked a bug that is implementing name and icon chooser, thanks to <strong>Habib</strong>’s mention.</p>
<h3>Beginning</h3>
<p>I finally took a bug to work on, but I got other issue! For some reasons, Webmaker always displayed empty page after I logon in. No matter what I did like cleaning up cookies, deleting account, and re-clone the repository, nothing’s working until the team fixed the issue. This makes me realizing that sometimes there are uncertainties in an open-source project. I should not always assume everything is good and be too late to start my work.</p>
<h3>Webmaker</h3>
<p>Finally, I started implementing the name &amp; icon chooser. This bug is quite simple because it is an implementation like I did in Filer contribution. However, it turned out a problem. Icon chooser requires a function of generating a new icon with certain icon image and custom circle color, while there were no information about how an icon is generated and where it is stored. Therefore, I spent too much time on writing code for icon generation and thinking about how I should do it. Then, I started asking on IRC channel because I thought I was doing wrong. Thanks to <strong>thisandagain</strong>, who told me that the custom icon details were actually missing, they are going to use the noun project for generating icons. At the end, I finally finish the implementation partially and made a pull request.</p>
<h3>Conclusion</h3>
<p>In the process of contribution, I realize that communication is really important for not only the whole team but also myself. The community plays a big role of helping yourself and helping others in order to help the project moving forward. If I did it earlier and asked people aggressively, I would not be so confused about the bug in the first place. By the way, I’d like to say thank you also to <strong>jbuck</strong> for his help of guiding me to use canvas for icons generation.</p>
