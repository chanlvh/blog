---
id: 280
title: 'Day 2 &#8211; Symbolic link vs Hard link'
date: 2016-05-12T21:59:42+00:00
author: Chan Le
layout: post
guid: http://blog.chan.io/?p=280
permalink: /day-2-symbolic-link-vs-hard-link/
image: /wp-content/uploads/ka2ab.jpg
categories:
  - Tech
---
`ln foo foo-hard`
`ln -s foo foo-soft`

Hard link is link to the file on disk, symbolic link is link to the file name of that file

Hence, if you change the original file name, the symbolic link will broke, but the hard link will not.
