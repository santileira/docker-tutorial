# Commands

## List of your running containers 

`docker ps` or `docker container ls`

## Execute docker image

`docker run <image-name>`

ex: `docker run hello-world`

## List of your images that was downloaded to your machine

`docker image ls`

## List of your stopped containers

`docker ps -all` or `docker container ls -all`

## Build an image

`docker build --tag=<image-name> <path where dockerfile is>`

ex: ` docker build --tag=friendmyhello /Users/sleira/Personal/Projects/docker-tutorial/python`

## Run the app

Run the app mapping your machine's port to the container's published port 80 using -p.

`docker run -p <machine's port: container's port> <image-name>`

ex: `docker run -p 4040:80 friendmyhello`

Run the app in the background adding the parameter `-d`, in deteched mode:

`docker run -d -p <machine's port: container's port> <image-name>`

ex: `docker run -d -p 4040:80 friendmyhello`

## Stop container

`docker container stop <container_id>`

ex: `docker container stop c7efb717299f`

## Log in to the Docker public registry on your local machine

`docker login`

## Tag image

`docker tag <image name> <username>/<repository>:<tag>`

ex: `docker tag friendmyhello sleira/get-started:part2`

## Push image

`docker push <username>/<repository>:<tag>`

ex: `docker push sleira/get-started:part2`

## Run your new load-balanced app

`docker stack deploy -c <docker-compose-file> <name>`

ex: `docker stack deploy -c docker-compose.yml getstartedlab`

## List of apps/stacks

`docker stack ls`

## List of running services associated with an app 

`docker service ls`

if you want to search one service you can run:

`docker stack services <service-name>`

ex: `docker stack services getstartedlab`

## List of tasks by service name

A single container running in a service is called a `task`.

`docker service ps <service-name>`

ex: `docker service ps getstartedlab_web`

## Inspect task or container

`docker inspect <task id or container id>`

## Tear down an application

`docker stack rm <app-name>`

ex: `docker stack rm getstartedlab`

## Enable swarm mode and make your current machine a swarm manager

`docker swarm init --advertise-addr <ip>`

ex: `docker swarm init --advertise-addr 192.168.99.100`

## Join other machines as workers

`docker swarm join --token <token> <ip>:<port>`

ex: `docker swarm join --token SWMTKN-1-108jeocx4w6e8ro537lksj50yot81a9pwmrlqyuye7d2g900wy-a6nxu7jgpfkzdorv9ytwtjpob 192.168.99.100:2377`

## Create virtual machine

`docker-machine create --driver <driver-name> <virtual-machine-name>`

ex: `docker-machine create --driver virtualbox myvm1`

## List virtual machines

`docker-machine ls`

## Connect to virtual machine and send commands

`docker-machine ssh <virtual-machine-name> "<command>"`

ex: `docker-machine ssh myvm1 "docker swarm init --advertise-addr <myvm1 ip>"`

## List nodes

`docker-machine ssh <virtual-machine-name> "docker node ls"`

ex: `docker-machine ssh myvm1 "docker node ls"`

## Leave swarm

`docker swarm leave --force`    


