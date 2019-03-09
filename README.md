# Unclephil Docker build environment

A part of my global Docker usage

Those files are destinated to my own usage, you can use too but at your oww risk

## Sources 
- Jessie Frazelle, the DoDG (Docker on Desktop Godess); @jessfraz, https://github.com/jessfraz, https://hub.docker.com/jess 
- Some additional sources
  - https://medium.com/redbubble/running-a-docker-container-as-a-non-root-user-7d2e00f8ee15

# Purpose of these repo
* Ability to build some of those container [docker-build]

# Other part of the environment
* Ability to launch some compose environment [docker-compose] 
* Ability to run docker on desktop environment (ala Jess)  [docker-bin]

# dependencies
- docker for lx
- traefik reverse proxy, because I prefer port 80   
- hostess to adapt local hosts file (https://github.com/cbednarski/hostess)

# My tools
* docker himself
* docker-compose
* docker-app 
* dive
* dockly

# DOD usage 
- On Linux, put or simlink necessary bin files somewhere in the executable path
- run it and point your client on the ad-hoc name/port/whatever

