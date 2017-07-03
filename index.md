# unblinkingBot  

![Logo](img/unblinkingbot_192x192.png)  

___

## tl;dr  

```Text
jmg1138       | @unblinkingbot get me the camera list  
unblinkingbot | Here are the camera names that you requested:  
              | • office  
              | • driveway  
              | • kitchen  
jmg1138       | @unblinkingbot get me a snapshot of the driveway camera
unblinkingbot | Here's that picture of the driveway that you wanted.
              | ╒════════════════════════╕
              | │                        │
              | │                        │
              | │                        │
              | ╘════════════════════════╛
jmg1138       | thanks @unblinkingbot  
unblinkingbot | That's my name @jmg1138, don't wear it out! 
```

## About  

The unblinkingBot is a surveillance-system assistant.  

It is an application that runs on your own server (such as a [Raspberry Pi](https://www.raspberrypi.org/products/)), providing an interface between your surveillance system and your [Slack team](https://get.slack.help/hc/en-us/articles/115004071768). It connects to [Slack](https://slack.com/) as a [bot-user](https://api.slack.com/bot-users), and you talk to it using the [Slack application](https://get.slack.help/hc/en-us/articles/201746897-Slack-apps-for-computers-phones-tablets).  

If you ask the unblinkingBot for a snapshot from one of your surveillance cameras, it replies with the picture, right there in the chat window.  

Documentation is available via the wiki:  

- [unblinkingBot wiki](https://github.com/nothingworksright/unblinkingbot/wiki) (for amd64 systems)  
- [unblinkingPi wiki](https://github.com/nothingworksright/unblinkingbot_pi/wiki) (for armv7hf systems, like Raspberry Pi)  

🛈 __Note__: _unblinkingBot is an alpha, open-source project._  

## Why  

I wanted to access my [motionEyeOs](https://github.com/ccrisan/motioneyeos/wiki) surveillance system from outside of my home network (while away from home for example), without a static IP address, without a Dynamic DNS service, and without exposing ports to the Internet.  

## How  

### [Slack](https://slack.com/)  

The unblinkingBot is a [Slack bot](https://api.slack.com/bot-users). [Slack](https://github.com/slackhq) offers a real-time messaging service that many people are already using and familiar with, and the [Slack API](https://api.slack.com/) is great. The [Slack Developer Kit for Node.js](https://slackapi.github.io/node-slack-sdk/) is a wrapper module for the Slack [RTM](https://api.slack.com/rtm) and [Web](https://api.slack.com/web) APIs.  

### [systemd](https://github.com/systemd/systemd)  

The bot runs as a [systemd](https://github.com/systemd/systemd) based service so that it starts automatically, runs unattended for long periods of time, and recovers gracefully in there are any unforseen crashes.  

### [Docker](https://github.com/docker)  

Installing and running the bot in a single step is possible with [Docker](https://github.com/docker) . Although it is possible to install the bot in a Linux system using the systemd service file, enable the service, start the service, and verify that the service is running, those steps might appear complicated for someone unfamiliar with systemd, Linux, sudo, etc. Alternatively, the bot can be run inside of a [Docker](https://github.com/docker) container using a single ```docker run``` command.  

### Web Front-End  

Once running, setting up the bot is as simple as using a web page. The bot serves up a web front-end using [Express](https://github.com/expressjs/express/), [Socket.IO](https://github.com/socketio/socket.io), and [Pug](https://github.com/pugjs/pug). From the web interface, a user can save their unique [Slack bot-user](https://api.slack.com/bot-users) token, save surveillance system integration details, etc.  

## Source Code Repositories  

There are separate repositories for amd64 and armv7hf CPU architectures.  

[nothingworksright/unblinkingbot](https://github.com/nothingworksright/unblinkingbot) (amd64)  
[nothingworksright/unblinkingbot_pi](https://github.com/nothingworksright/unblinkingbot_pi) (armv7hf, such as a [Raspberry Pi](https://www.raspberrypi.org/products/))  

___

© 2017 [__nothingworksright__](https://github.com/nothingworksright)  

View the [source code repository that powers this website](https://github.com/nothingworksright/unblinkingbot_website)  
