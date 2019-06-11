# Strudel Web

This page contains the instruction to build Strudel Web application.

## Pre-requisite
- HAProxy server (see HAPROXY.md)
- A server running Ubuntu 18.04 and Docker
- A configured `strudel-web.properties`. An example of the file is provided under `conf/strudel-web.properties.example`.

## Building Strudel Web
- `git clone git@github.com:monash-merc/strudel-docker-public.git strudel-web`
- `cd strudel-web`
- Copy or move `strudel-web.properties` to the `conf/` folder
- `./build.sh`
- `./run.sh` to start the container


## Configuration Files
The `conf/` directory contains the configuration files necesarry to run Strudel Web.
1. `guacamole.properties` --> Auth configuration file for Guacamole Client
2. `nginx.conf` --> Configuration file for nginx proxy server
3. `setenv.sh` --> Catalina startup configuration file
4. `strudel-web.log4j2.xml` --> Configuration file for Strudel Web app logging
5. `strudel-web.properties.example` --> Auth configuration for Strudel Web
