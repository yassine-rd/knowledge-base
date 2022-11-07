# Introduction to Docker

![Docker illustration](../docker/images/docker-logo.png)

**What is Docker ?**

**Docker** is a suite of platform as a service ([[PaaS]]) products that allows users to separate applications from infrastructures (OS-level virtualization), so the software can be delivered quickly in packages called **[[containers]]** (think microservices).

**What does Docker Offer?**

Docker offers various tools such as :

- Docker Build: Developer tools for building container [[images]]  
- Docker Hub: Allows users to share images with your team or with the public  
- Docker Engine: A container runtime that runs in almost any environment. The engine creates a server-side daemon that hosts images, containers, networks, and storage volumes.

**What problem is Docker trying to solve ?**

Let's say you have 3 different JavaScript applications you plan to host on single server. Each of these applications uses is written in a different version of Javascript, since we cannot have 3 different versions of JavaScript installed on the same machine this prevents us from hosting all three applications on the same machine.

**Solution :**

The solution is that **Docker** containers will run each version in different containers, in our case, there are three separate versions of Javascript. So each version would run in its own Docker container. In short, Docker would virtualize the operating system of the host on which it is installed.

## Docker CLI configuration file (`config.json`) properties

Use the [[docker-cli]] configuration to customize settings for the `docker` CLI. The configuration file uses JSON formatting, and properties.

> By default, configuration file is stored in `~/.docker/config.json`.

## Docker containers

`TODO : Finish writing docker containers section`

## Docker images

`TODO : Finish writing docker images section`

## Docker volumes

- Docker **[[volumes]]** are created between the container and the filesystem area.
- They allow sharing data (files and folders) between **host** and **container**, and also between **containers**.

## Dockerfile

Docker can build images automatically by reading the instructions from a `Dockerfile`. A [[docker-file]] is a text document that contains all the commands a user could call on the command line to assemble an image.
