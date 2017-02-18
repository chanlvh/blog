---
id: 266
title: 'Day 1 - Chef nightmare &#038; setup script security problem'
date: 2016-05-12T13:02:23+00:00
author: Chan Le
layout: post
guid: http://blog.chan.io/?p=266
permalink: /day-1-chef-nightmare/
image: /wp-content/uploads/pic-chef-logo.png
categories:
  - Projects
  - Tech
---
I decided to automate setting up my server to start this project. The goal is to install and config dokku automatically so that next installation will take 1-2s max. Because I already have some experience with chef from the early days of my career, I decided to go with it and spent several hours re-learn several concepts. The way chef use metaphor make things a bit confusing, I ended up doing 2 tutorial to get familiar with everything: [Learn the basics](https://learn.chef.io/learn-the-basics/ubuntu/) and [Managing a node](https://learn.chef.io/manage-a-node/ubuntu). Anyway here are something I re-learned:

*   cookbook store all the scripts to manage a service (1 for apache, 1 for dokku...)
*   a recipe is the script to do 1 thing: install, add a user,,,
*   knife is the tool use on your workstation to test/ develop those scripts
*   kitchen is their test tool
*   solve all upload and dependency problems using berks, the knife site install tool is broken. I ended up spending several hours trying to fix dependency problems before realizing this tool exist
*   Use this command to bootstrap a new vagrant node and run default recipe of dokku cookbook: `knife bootstrap localhost:2222 --ssh-user vagrant --ssh-password vagrant --sudo --use-sudo-password --node-name testNode --run-list 'recipe[dokku]'`

# Chef problems

This turns out to be a nightmare. Cookbooks - the main things we used to build server with chef aren't updated or does not sync with the other cookbook update. Berks helps a lot, but there are still bugs here and there. I stuck at installing herokuish for dokku - for some reason chef just can't move past that point. Some googling point me to an unfixed bug of chef. Tung told me to consider using bash file instead, since I'm going to do it only a few times & it's much simpler than chef - he also think chef doesn't work most of the time. Turns out bash [just works](https://github.com/chanlvh/config)!

# Security issue

I thought a bit about whether I should publish the bash script to setting up my server. On one hand, publishing it is a security risk - identity of all services used to build my server are exposed to the public. On the other hand, I think everything I did in this 100 days campaign should be public somewhere. Since I will write a lots about all services and technical things I learned during those days, someone can read my blog and obtain as much information about that server as reading the setup.sh file. Hence, I decided to put everything on github.
