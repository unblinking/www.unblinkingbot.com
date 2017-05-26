# unblinkingBot  

A home-surveillance-system assistant. The unblinkingBot is a Slack bot, hosted on your home server.  

## Source Code Repositories  

### [nothingworksright/unblinkingbot](https://github.com/nothingworksright/unblinkingbot)  

For amd64 based systems. This repository is setup on [Docker Hub](https://hub.docker.com/r/nothingworksright/unblinkingbot/) as an automated build.  

The Dockerfile starts the build from [nothingworksright/amd64_debian_jessie_node](https://hub.docker.com/r/nothingworksright/unblinkingbot/~/dockerfile/), which is itself an automated build which starts from [resin/amd64-debian:jessie](https://hub.docker.com/r/resin/amd64-debian/).  

### [nothingworksright/unblinkingbot_pi](https://github.com/nothingworksright/unblinkingbot_pi)  

For the Raspberry Pi (armv7hf based systems). This repository is setup on [Docker Hub](https://hub.docker.com/r/nothingworksright/unblinkingbot_pi/). This build is completed manually on a Raspberry Pi, before pushing the container image to Docker Hub.  

The Dockerfile starts the build from [nothingworksright/armv7hf_debian_jessie_node](https://hub.docker.com/r/nothingworksright/armv7hf_debian_jessie_node/), which is a manually built container image which starts from [resin/armv7hf-debian:jessie](https://hub.docker.com/r/resin/armv7hf-debian/).  
