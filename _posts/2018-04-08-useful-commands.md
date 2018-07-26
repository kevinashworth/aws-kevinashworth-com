---
layout: single
status: publish
published: true
title: Useful commands for the terminal, i.e, a page I will need to look at again and again
date: 2018-04-08 14:26:38
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
