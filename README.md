# Purpose :
This repository helps you relocate homebrewed nodejs modules on mac.

## INSTALLATION Script for First time user


```
## Shell script support for npm modules migration
## For Mac, place this folder under /home/$USER/.npm
## brew install nodejs , please use brew edit to remove "without-npm"

alias ng1="npm list -g --depth=1"

function installnpm() {
	defaultNPM=$(npm | grep @ | awk '{print $2}')
	mkdir -p ~/.npm

	echo REF:https://nodesource.com/blog/configuring-your-npmrc-for-an-optimal-node-js-environment/

	echo "SETTING USER CONFIG---"
	npm config set init.author.name "Ralic Lo"
	npm config set init.author.email "ralic.lo.eng@ieee.org"
	npm config set init.author.url "http://www.life-fund.org"
	npm config set init.license "MIT"
	npm config set init.version "0.0.1"
	npm config set loglevel="warn"
	npm config set prefix "~/.npm"

	echo "SETTING GLOBAL CONFIG---"
	## This creates "~/.npm/etc/npmrc"
	npm config --global set prefix "~/.npm" 
	echo "export PATH=~/.npm/bin:$PATH" in your bashrc manually

	echo "INSTALLING live-server"
	## This createes "~/.npm/bin/live-sever" , "~/.npm/lib/node_modules/live-server"
	npm install live-server -g


	echo "Double Checking configs"
	## This prints out current configurations"
	npm config list 
	npm list -g --depth=1

	echo "Showing .npmrc setting" 
	## This .npmrc shall be copied to each project when you use npm init
	## So you can share node_modules in each project
	cat ~/.npmrc
}



```

## Donation ($1.0 USD) <a href="https://goo.gl/BTFKsk"><img src="https://cdn1.iconfinder.com/data/icons/banking/512/E1-256.png" width="30"></a> 

Link: (https://goo.gl/BTFKsk)

Wish these configurations helps you in the development and save your time. 
Shall you have any question, please send email to "ralic.lo.eng@ieee.org".
## REF: 
https://nodesource.com/blog/configuring-your-npmrc-for-an-optimal-node-js-environment/
