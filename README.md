# Hello World on Autopilot deliverd by SnowGlobe

(this is a fork of http://github.com/autopilotpattern/hello-world.git, intended to demonstrate
SnowGlobe for setup/teardown of containers).

## Build with Jenkins

The Jenkinsfile assumes that you have docker-plugin and snowglobe-plugin. It also assumes that there
is a docker cloud defined called 'docker'.

This will build the containers defined in this project, and associate a SnowGlobe configuration. This
can then be launched by looking at the build, then following the SnowGlobe link.

This configuration (which is in the snowglobe subdirectory) is akin to the docker-compose layout
controlling how the particular containers are wired together.


# Original Details:

1. `git clone git@github.com:autopilotpattern/hello-world.git`
2. `cd hello-world`
3. `docker-compose up -d`
4. `open http://localhost`

## Overview

The application is divided into 4 parts:
1. Frontend - nginx server rendering static assets
2. Consul - service catalog used to keep track of registered services
3. Hello - Node.js service responding with the word "Hello"
4. Hello - Node.js service responding with the word "World"

![hello-world diagram](hello-world.png)


