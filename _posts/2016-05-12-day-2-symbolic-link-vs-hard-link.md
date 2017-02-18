---
layout: post
title: 'Day 2 - Symbolic link vs Hard link'
date: 2016-05-12T21:59:42+00:00
author: Chan Le
permalink: /day-2-symbolic-link-vs-hard-link/
image: /uploads/ka2ab.jpg
---
`ln foo foo-hard`
`ln -s foo foo-soft`

Hard link is link to the file on disk, symbolic link is link to the file name of that file

Hence, if you change the original file name, the symbolic link will broke, but the hard link will not.
