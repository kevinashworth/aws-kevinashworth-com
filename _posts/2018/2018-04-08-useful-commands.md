---
layout: single
title: Useful commands for the terminal, i.e, a page I will need to look at again and again
date: 2018-04-08 14:26:38
last_modified_at: 2018-10-15 18:38:00
categories:
- Blog
tags:
- CLI
- Terminal
- Programming
- Development
- macOS
---
To delete all those pesky .DS_Store files and see what they were:

`find . -name .DS_Store -type f -delete -print`

To list all the globally installed node packages, but cleanly:

`npm list -g --depth=0`

To delete all local branches that are already merged into the currently checked out branch:

`git branch --merged | egrep -v "(^\*|master|dev)" | xargs git branch -d`
