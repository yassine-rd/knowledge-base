
# Dockerfile example using nginx

First, let's make sure we're in the correct folder : `cd /Users/kheey/Dev/docker/website`

```dockerfile
# We use an image already existing as a base image
# We will never build an image from scratch
# In our case, we will be using nginx image with the latest tag as a base image
FROM nginx:latest

# We want to add the entire present working directory into a specific destination
# With nginx, /usr/share/nginx/html is where the static content should live
ADD . /usr/share/nginx/html
```

## Building image using Dockerfile

> We have to specify few parameters, at least the tag parameter (latest in our case)
> The . indicate that it will look for a Dockerfile on the present working directory

`docker build --tag NAME:latest .`

## .dockerignore

A **.dockerignore** filesallows you to mention a list of files and/or directories which you might want to ignore while building the image. This would definitely reduce the size of the image and also help to speed up the docker build process.
