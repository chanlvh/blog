---
id: 284
title: 'Day 2 - Bash learning'
date: 2016-05-13T05:06:06+00:00
author: Chan Le
layout: post

permalink: /day-2-bash-learning/
image: /uploads/04daa4a.jpg
categories:
  - Tech
---
Bash works surprisingly well. I'm able to automate all of my deployment task using bash, including database creation and error checking. Even though it's a bit verbose, it's works fine! (unlike *cough*chef*cough*) A few things I learned today about bash scripting: check if variable exist `if [ -z ${VAR_NAME+x} ]; then DO_THINGS fi` assign result of command to an variable

`CURRENT_PATH=$(git remote get-url dokku)`

run command over ssh

`ssh -t root@$HOST_NAME -- dokku apps:create $APP_NAME`

check if string contains another string

`if [[ $CURRENT_PATH == *"No such remote"* ]]; then`

check if status code != 0

`if [ $? -ne 0 ]; then`

check if file exists

`if [ -f "init.sh" ];`

exit script on error

`set -e`

print command out before execute

`set -x`

function declaration

`error() { DO_STUFFS }`

print to error out

`>&2 echo 123`

print with color

`echo "$(tput setaf 1)TEXT_HERE$(tput sgr0)"`

bash find and replace

`sed -i -e 's/ABC/DEF/g' ~/.bashrc`

bash include

`source common.sh`

generate key silently

`ssh-keygen -q -t rsa -C "root@chan.io" -N "" -f ~/.ssh/id_rsa`

download text file then pipe its content to another command

`curl -sS https://raw.githubusercontent.com/chanlvh/config/master/id_rsa.pub | sshcommand acl-add dokku chanlvh`

run command as another user

`su - dokku -c 'whoami'`

for each sub folder

```for D in `find .. -maxdepth 1 -mindepth 1 -type d` do cd $D done```

