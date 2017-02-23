# Start Create Development Environment

## nodejs
$ cd nodejs

### create/get images
$ docker build -t arukmn/node-image .
$ docker pull redis

### launch containers
$ docker compose up

### get local app container-id
$ docker ps

### attach container
$ docker exec -it CONTAINER_ID /bin/bash

### confirm redis host
$ host redis

