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

`docker build --tag=<name> <path where dockerfile is>`

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
