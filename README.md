# docker-tutorial

In this repository I will follow the Docker page tutorial. (https://docs.docker.com/get-started/) 

In the folder `python` is an application to follow the tutorial.

In the `COMMANDS.md` file is most common commands to use in Docker.

## Services

### What are the Services in Docker?

Services are really just “containers in production.” A service only runs one image, but it codifies the way that image runs—what ports it should use, how many replicas of the container should run so the service has the capacity it needs, and so on.

## Swarms

### What is the swarm in Docker? 
A swarm is a group of machines that are running Docker and joined into a cluster.

### Types

- Managers: are the only machines in a swarm that can execute your commands, or authorize other machines to join the swarm as workers.
- Workers: are just there to provide capacity and do not have the authority to tell any other machine what it can and cannot do.
