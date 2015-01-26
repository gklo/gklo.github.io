---
layout: post
title: Brackets (Release 0.4)
date: 2014-12-11 06:34:28.000000000 -05:00
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
<https://github.com/adobe/brackets/issues/10071>  
<https://github.com/adobe/brackets/pull/10141>

<br/> As the last release of the course, I decide to contribute to Adobe Brackets.  It is because Brackets is a big project and I heard good things about it from <strong>Habib</strong>.  When the first time I check out Bracket, I was surprised.  Brackets code are really well organized, fully commented and clean.  It made me revise my original impression of Adobe (since Adobe Flash).  I become having passion to work for this project.

<br/> The bug I picked for this release is implementing file type detection for extensionless file.  It was a quite challenging bug to me.  I decided to implement for bash script only at the moment.  At the beginning, it was not easy to find information about the syntax highlighting.  After a while, I realized that Brackets uses CodeMirror to handles the languages and syntax highlighting.  Though, I had no luck with it.  I ended up getting hints from the file LanguageManager.js and Document.js.

<br/> Then, here came the question about the proper way to implement the functionality.  After getting help from<strong> redmund </strong>on irc, I got the ideas which are keeping detection in LanguageManager.js and it should not depend on Document object.  The first attempt of implementation wasn't that good, but I think it was on the right track.  After getting a code review by <strong>dangoor, </strong>I got a clear mind about the code to write.  Instead of hard coding, adding new attribute to language object is proper way to normalize the detection process.  At the end of Wednesday, I finally finish it and wait for new feedbacks.

<br/> It was such a good experience to contribute to Brackets. Since it is a serious project, it encouraged me to be more careful when writing my code.  Also, there are doc comments,  indention, and unit test which are needed to be done whenever a new feature implemented.  Overall, I think I got interested in this kind of challenge project.  It is helpful for learning.
