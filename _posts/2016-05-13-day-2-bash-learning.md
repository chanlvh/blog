---
id: 284
title: 'Day 2 &#8211; Bash learning'
date: 2016-05-13T05:06:06+00:00
author: Chan Le
layout: post
guid: http://blog.chan.io/?p=284
permalink: /day-2-bash-learning/
image: /wp-content/uploads/04daa4a.jpg
categories:
  - Tech
---
Bash works surprisingly well. I'm able to automate all of my deployment task using bash, including database creation and error checking. Even though it's a bit verbose, it's works fine! (unlike *cough*chef*cough*) A few things I learned today about bash scripting: check if variable exist `if [ -z ${VAR_NAME+x} ]; then DO_THINGS fi` assign result of command to an variable

`<span class="s1">CURRENT_PATH</span><span class="s2">=</span><span class="s3">$(</span><span class="s4">git remote get-url dokku</span><span class="s3">)</span>`

run command over ssh

`<span class="s1">ssh -t root@$HOST_NAME -- dokku apps:create $APP_NAME</span>`

check if string contains another string

`<span class="s1">if [[</span> <span class="s3">$CURRENT_PATH</span> <span class="s1">==</span> <span class="s2">*</span><span class="s1">"</span><span class="s4">No such remote</span><span class="s1">"</span><span class="s2">*</span> <span class="s1">]];</span> <span class="s1">then</span>`

check if status code != 0

`<span class="s1">if [</span> <span class="s3">$?</span> <span class="s1">-ne</span> <span class="s4">0</span> <span class="s1">];</span> <span class="s1">then</span>`

check if file exists

`if [ -f "init.sh" ];`

exit script on error

`set -e`

print command out before execute

`<span class="s1">set</span> <span class="s3">-x</span>`

function declaration

`error() { DO_STUFFS }`

print to error out

`>&2 echo 123`

print with color

`<span class="s1">echo</span> <span class="s1">"</span><span class="s3">$(tput setaf</span> <span class="s2">1</span><span class="s3">)</span><span class="s2">TEXT_HERE</span><span class="s3">$(tput sgr0)</span><span class="s1">"</span>`

bash find and replace

`<span class="s1">sed</span> <span class="s2">-i</span> <span class="s2">-e</span> <span class="s3">'</span><span class="s4">s/ABC/DEF/g</span><span class="s3">'</span> <span class="s1">~/.bashrc</span>`

bash include

`<span class="s1">source common.sh</span>`

generate key silently

`<span class="s1">ssh-keygen</span> <span class="s2">-q</span> <span class="s2">-t</span> <span class="s1">rsa</span> <span class="s2">-C</span> <span class="s3">"</span><span class="s4">root@chan.io</span><span class="s3">"</span> <span class="s2">-N</span> <span class="s3">""</span> <span class="s2">-f</span> <span class="s1">~/.ssh/id_rsa</span>`

download text file then pipe its content to another command

`<span class="s1">curl</span> <span class="s2">-sS</span> <span class="s1">https://raw.githubusercontent.com/chanlvh/config/master/id_rsa.pub | sshcommand acl-add dokku chanlvh</span>`

run command as another user

`su - dokku -c 'whoami'`

for each sub folder

`for D in `find .. -maxdepth 1 -mindepth 1 -type d` do cd $D done`
