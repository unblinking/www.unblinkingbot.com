# unblinkingBot  

A home-surveillance-system assistant bot.  

![Logo](img/unblinkingbot_192x192.png)  

___

## About  

The unblinkingBot is a [Slack bot](https://api.slack.com/bot-users), hosted on your home server. The bot acts as an assistant, interfacing with your home-surveillance-system such as [motionEyeOs](https://github.com/ccrisan/motioneyeos/wiki).  

## Why  

I wanted a way to access my [motionEyeOs](https://github.com/ccrisan/motioneyeos/wiki) system from outside of my home network (while away from home for example), without a static IP address, without a Dynamic DNS service, and without exposing ports to the Internet.  

## How  

I decided to accomplish this using a [Slack bot](https://api.slack.com/bot-users). [Slack](https://slack.com/) offers a real-time messaging service that I was already using and familiar with. The [Slack API](https://api.slack.com/) is great, and I wanted to use [Node.js](https://github.com/nodejs) for this project, so I went with the [Slack Developer Kit for Node.js](https://slackapi.github.io/node-slack-sdk/).  

For reliability, the bot needed to start automatically, run unattended for long periods of time, and recover from possible crashes. For this, the bot runs as a [systemd](https://github.com/systemd/systemd) based service.  

Installing and running the bot should require minimal steps, maybe even just a single step. Although it is possible to install the bot in a Linux system using the systemd service file, enable the service, start the service, and verify that the service is running, those steps might appear complicated for someone unfamiliar with systemd, Linux, sudo, etc. Alternatively, the bot can be run inside of a [Docker](https://github.com/docker) container using a single ```docker run``` command.  

Once running, setting up the bot needed to be simple, so I gave it a web frontend using [Express](https://github.com/expressjs/express/), [Socket.IO](https://github.com/socketio/socket.io), [Pug](https://github.com/pugjs/pug), and [Level](https://github.com/Level/level). From the web UI a user can save their unique [Slack bot-user](https://api.slack.com/bot-users) token, choose a default [Slack](https://slack.com/) channel or user for the bot to deliver notifications to, save surveillance system integration details, etc.  

## Source Code Repositories  

There are separate repositories for amd64 and armv7hf CPU architectures.  

### [nothingworksright/unblinkingbot](https://github.com/nothingworksright/unblinkingbot) (amd64)  

For amd64 based systems.  

#### The amd64 Docker image  

This repository is setup on [Docker Hub](https://hub.docker.com/r/nothingworksright/unblinkingbot/) as an automated build.
The Dockerfile starts the build from [my amd64 debian jessie node image](https://hub.docker.com/r/nothingworksright/amd64_debian_jessie_node/),
which is itself an automated build which starts from [resin/amd64-debian:jessie](https://hub.docker.com/r/resin/amd64-debian/),
which is built on top of the [official Debian Docker image](https://hub.docker.com/_/debian/).  

### [nothingworksright/unblinkingbot_pi](https://github.com/nothingworksright/unblinkingbot_pi) (armv7hf)  

For the Raspberry Pi (armv7hf based systems).  

#### The armv7hf Docker image  

This repository is setup on [Docker Hub](https://hub.docker.com/r/nothingworksright/unblinkingbot_pi/). This build is completed manually on a Raspberry Pi, before pushing the container image to Docker Hub. The Dockerfile starts the build from [my armv7hf debian jessie node image](https://hub.docker.com/r/nothingworksright/armv7hf_debian_jessie_node/), which is also a manually built container image which starts from [resin/armv7hf-debian:jessie](https://hub.docker.com/r/resin/armv7hf-debian/), which is built on top of the [official Debian Docker image for armhf](https://hub.docker.com/r/armhf/debian/).  

___

&copy; 2017 [__nothingworksright__](https://github.com/nothingworksright)  
View the [source code repository for this website](https://github.com/nothingworksright/unblinkingbot_website)  
