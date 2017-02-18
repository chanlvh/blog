---
id: 270
title: 'Day 1 &#8211; Vim regex turns comment into echo'
date: 2016-05-12T12:37:02+00:00
author: Chan Le
layout: post
guid: http://blog.chan.io/?p=270
permalink: /day-2-vim-regex/
image: /wp-content/uploads/regex.jpg
categories:
  - Tech
---
While building my bash scripts to setting up server, I figure out this cool find and replace regex in vim. Originally I leave a comment in front of each command in my bash file to document what I'm doing there. After a while I realized that it's probably better if I print it out directly to the screen. So here is the regex to convert "# comment" into "echo "COMMENT"" (also changing case of the comment and add a pair of quote) `:%s/^# \(.*\)$/echo \U"======> \1"\E/gc`

*   `:%s/` is just the starting part of vim find and replace command
*   `^` is beginning of line, together with `#` and space form the pattern at the beginning of each comment
*   `\(.*\)` get the whole comment to group 1
*   `$` mark the end of line
*   `/` mark the end of find part, here comes the replace part:
*   i don't have to mark begin & end of line here, so it started off with `echo` as the starting pattern
*   `\U` make everything after that upper case
*   `\1` return the  group 1 saved above
*   `\E` end the uppercase
*   `/gc` means replace global & confirm before each replacement
