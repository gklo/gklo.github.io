---
layout: post
title: Koji build system overview
date: 2015-07-03T17:07:37-04:00
categories:
- open-source
tags:
- open-source
status: publish
type: post
published: true
comments: true
---

As being Pidora\'s maintainer in winter, most of my time was spent on Koji, a package building system created by Fedora engineers.  Packing a repository scale of packages is a task that could take huge amount of time to complete, and it is unrealistic to build on your computer one by one.  Therefore, Koji is created.  The purpose of having koji is making a multi-user, reusable, scalable package building system.  There are a few components in the Koji system:

![Koji build system graph]({{site.url}}/assets/img/2015-07-03-koji-build-systems-overview/koji_overview.png)

- **Koji-hub** - Central service of koji - Receiving commands from client, assigning/passing tasks to other components based on httpd and XML-PRC call.

- **Builders/Hosts (kojid)** - machines that are used for building packages only.  Once the daemon kojid on it receives any task from koji-hub, the builder creates a mock chroot and builds packages in it.

- **Storage** - Simply a network-attached storage mounted at */mnt/koji* on any koji machines, storing all the build logs and package files.
    - Koji repositories - collections of packages that have already built on koji.  Since a koji repo is basically a yum repo, testing it becomes easy and convenient.

- **Kojira** - In order to make a built package available for building other packages, koji repository needs to be regenerated.  Kojira is a daemon automatically detects any new changes and create a repo regeneration task.

- **Postgresql database** - koji user and package database

- **koji web** - A web interface allowing user to quickly check about current tasks, build status, host status, reports, etc.

- **koji client** - A workstation contains koji user certificate.  Once the client is authenticated, user can manage packages on koji server using koji cli commands.
