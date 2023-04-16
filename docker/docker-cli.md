# Docker Command-line Interface

> A list of my commonly used Docker commands**

## Running Containers

COMMAND | DESCRIPTION
---|---
`docker run -d IMAGE:TAG` | Start a new container in “detached” mode
`docker run -d --name NAME IMAGE` | Start a new container in “detached” mode, and set a custom name
`docker run -d -p HOSTPORT:CONTAINER_PORT IMAGE` | Start a new container in “detached” mode (in the background) and with mapped ports

- If `TAG` isn't specified, `latest` will be used by default
- "detached" mode means that a container is running in the background
- Docker flags can be combined like this `docker run -dp ...`
- You can map multiple ports to the container's port like this `docker run -d -p 8080:80 -p 3000:80 IMAGE:TAG`

## Inspecting Containers

COMMAND | DESCRIPTION
---|---
`docker ps` | List running containers
`docker ps -a` | List all containers, including stopped
`docker ps --format="TEMPLATE"`| Pretty-print running containers using a template
`docker logs CONTAINER` | Show a container output
`docker logs -f CONTAINER` | Follow a container output
`docker top CONTAINER` | List the processes running in a container
`docker diff` | Show the differences with the image (modified files)
`docker inspect` | Show information of a container (json formatted)

> In case you have multiple containers running at the same time, the output of a simple `docker ps` can be a little bit hard to read. So what we can do is simply use a `--format` flag and set it equal to `$FORMAT`, an environment variable for a narrow format. It is used like this : `docker ps --format=$FORMAT`

## Containers Management

> `CONTAINER` might be either `CONTAINER_ID` or `CONTAINER_NAME`

COMMAND | DESCRIPTION
---|---
`docker start CONTAINER` | Start a container
`docker stop CONTAINER` | Graceful stop a container
`docker kill CONTAINER` | Kill (SIGKILL) a container
`docker restart CONTAINER` | Graceful stop and restart a container
`docker pause CONTAINER` | Suspend a container
`docker unpause CONTAINER` | Resume a container
`docker rm CONTAINER` | Remove a container

## Containers Bulk Management (Nested)

COMMAND | DESCRIPTION
---|---
`docker stop $(docker ps -q)` | To stop all the running containers
`docker stop $(docker ps -a -q)` | To stop all the stopped and running containers
`docker kill $(docker ps -q)` | To kill all the running containers
`docker kill $(docker ps -a -q)` | To kill all the stopped and running containers
`docker restart $(docker ps  -q)` | To restart all  running containers
`docker restart $(docker ps -a -q)` | To restart all the stopped and running containers
`docker rm $(docker ps  -q)` | To destroy all running containers
`docker rm $(docker ps -a -q)` | To destroy all the stopped and running containers
`docker pause $(docker ps  -q)` | To pause all  running containers
`docker pause $(docker ps -a -q)` | To pause all the stopped and running containers
`docker start $(docker ps  -q)` | To start all  running containers
`docker start $(docker ps -a -q)` | To start all the stopped and running containers
`docker rm -vf $(docker ps -a -q)` | To delete all containers including its volumes use
`docker rmi -f $(docker images -a -q)` | To delete all the images

## Volumes

> We will be using the nginx docker image as an example for docker volumes
> `CONTAINER` might be either `CONTAINER_ID` or `CONTAINER_NAME`

COMMAND | DESCRIPTION
---|---
`docker run -dp 8080:80 --name website -v $(pwd):/usr/share/nginx/html` | Start a new container named then mount the entire present working directory to this container
`docker exec -it CONTAINER /bin/bash` | Open an interactive shell inside a container (there is no bash in some images, use /bin/sh)

## Images

Docker images are templates for creating an environment of yout choice.

COMMAND | DESCRIPTION
---|---
`docker image ls` | List all the local image
`docker rmi IMAGE_ID` | Delete docker image with id
