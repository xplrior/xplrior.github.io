---
layout: default
---

# Docker Commands

## Add User to Group

`sudo usermod -aG docker ${USER}`

## Commands

### Clean Local Machine

`docker system prune -af --volumes`

### Build Docker Image

`docker build --tag=nameofimage .`

### List Running Process/Containers

`sudo docker ps -a --no-trunc`

### Stop All Containers

`docker kill $(docker ps -q)`

### Remove All Containers

`docker rm $(docker ps -a -q)`

### List Docker Images

`docker image ls`

### Remove All Docker Images

`docker rmi $(docker images -q)`

### Force Remove Docker Image

`docker rmi -f <IMAGE_ID>`

### Publish or Expose Port (-p, --expose)

This binds port 8080 of the container to TCP port 80 on 127.0.0.1 of the host machine. You can also specify udp and sctp ports.

`docker run -p 127.0.0.1:80:8080/tcp ubuntu bash`

or the following when running Apache2

`docker run -p 127.0.0.1:80:8080/tcp httpd`

### Exec into a running container

`docker exec -it <container-id> /bin/bash`

### Exec into a running container (Windows)

`docker exec -it <container-id> cmd`

### Run an image with an ENTRYPOINT command in interactive mode with the command /bin/bash

`docker run --entrypoint /bin/bash -it <image_name>`

### Run an image in interactive mode with the command /bin/bash mounting the host directory /var/app/current to the container directory /usr/src/app

`docker run -it -v /var/app/current:/usr/src/app/ <image_name> /bin/bash`

### Run an image in interactive mode with the command /bin/bash setting the environments variables FOO and BAR

`sudo docker run -it -e FOO=foo -e BAR=bar <image_name> /bin/bash`

### View logs for a container or service

`docker logs <container-id>`

### Inspect a container

`docker inspect <container-id>`

---

[back](../til.md)
