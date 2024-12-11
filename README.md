**README.md**

# Docker Introduction and Basics

## Introduction

Docker is a powerful tool for managing containers, providing developers with a consistent environment for developing and running applications or codebases. This document serves as a primer on Docker, covering essential concepts and commands.

## Docker Concepts

### Docker Image

An image is like a blueprint for containers. It includes the runtime environment, application code, dependencies, environment variables, and its own file system.

### Docker Container

A container is a running instance of an image. It is an isolated process outside the host computer's process.

### Dockerfile

A Dockerfile is a special type of file used to create custom Docker images. It contains instructions for building the custom image.

### .dockerignore File

This file specifies which files Docker should ignore during the build process, similar to .gitignore in Git.

### Docker Hub

Docker Hub is a repository similar to GitHub but for Docker. It hosts various images, including parent images that serve as base operating systems for other images.

### Docker Volume

A feature that maps files or directories in the local environment to those in Docker containers, enabling automatic updates between them.

### Docker Compose

A tool for defining and running multi-container Docker applications. It uses a YAML file to configure application services, making it easier to manage complex applications.

## Docker Cheatsheet

### Basic Commands

- `docker images`: Lists Docker images.
- `docker images -a`: Shows all containers.
- `docker run {container_name}`: Runs a Docker container/image.
- `docker ps`: Shows all active containers.
- `docker ps -a`: Shows all containers.
- `docker stop {container_name or container_id}`: Stops a container.
- `docker image rm {image_name}`: Deletes an image.
- `docker rmi {image_name}`: Deletes an image.
- `docker image rm {image_name} -f`: Deletes an image by force.
- `docker container rm {container_name or container_id}`: Deletes a container.
- `docker start {container_name or container_id}`: Starts a container in detached mode.
- `docker system prune -a`: Deletes everything in Docker.

### Running Containers

- Proper way to run a container with `-p port mapping` `-d detached mode runs in background` and `-v volume mounting`.
```bash
  docker run --name {container_name} -p {container_port:local_port} -d -v {path_in_system}:{path_in_container} {image_name}
```


### Docker Build

- `docker build -t {image_name} .`: Builds a Docker container with a tag.
- `docker build -t {name}:{version} .`: Builds a Docker container with a specific version.

### Docker Compose

- `docker-compose up`: Runs containers defined in docker-compose.yaml.
- `docker-compose down`: Stops containers.
- `docker-compose down --rmi all -v`: Removes everything, including containers and volumes.

### Docker Networking

- `docker network ls`: Lists all Docker networks.
- `docker network create {network_name}`: Creates a new Docker network.
- `docker network inspect {network_name}`: Displays detailed information about a Docker network.
- `docker network connect {network_name} {container_name}`: Connects a container to a Docker network.
- `docker network disconnect {network_name} {container_name}`: Disconnects a container from a Docker network.

### Docker Volume Management

- `docker volume ls`: Lists all Docker volumes.
- `docker volume create {volume_name}`: Creates a new Docker volume.
- `docker volume inspect {volume_name}`: Displays detailed information about a Docker volume.
- `docker volume prune`: Removes all unused Docker volumes.
- `docker volume rm {volume_name}`: Removes a specific Docker volume.

### Docker Image Management

- `docker pull {image_name}`: Pulls an image from Docker Hub.
- `docker push {image_name}`: Pushes an image to Docker Hub.
- `docker tag {source_image}:{source_tag} {target_image}:{target_tag}`: Tags a Docker image with a new name and/or tag.
- `docker commit {container_id} {image_name}:{tag}`: Creates a new image from a container's changes.

### Docker Inspection and Debugging

- `docker inspect {container_name_or_id or image_id}`: Displays detailed information about a Docker container or image depenying on what you passed to it .
- `docker logs {container_name_or_id}`: Displays logs from a Docker container.
- `docker exec -it {container_name_or_id} {command}`: Executes a command inside a running Docker container.
- `docker diff {container_name_or_id}`: Shows changes made to the filesystem of a Docker container.

### Docker Swarm

- `docker swarm init`: Initializes a Docker Swarm.
- `docker swarm join`: Adds a node to the Swarm.
- `docker service ls`: Lists all services in the Swarm.
- `docker service create`: Creates a new service.
- `docker node ls`: Lists all nodes in the Swarm.
- `docker stack deploy`: Deploys a new stack or updates an existing stack in the Swarm.

### Docker Registry

- `docker login`: Logs in to a Docker registry.
- `docker logout`: Logs out from a Docker registry.
- `docker search {image_name}`: Searches for an image on Docker Hub.
- `docker push {image_name}`: Pushes an image to a Docker registry.

### Docker System

- `docker system df`: Displays detailed information about Docker disk usage.
- `docker system info`: Displays system-wide information about Docker.
- `docker system prune`: Removes unused data such as stopped containers, dangling images, and networks.

# For more command or explanation on how to use any of them go to ChatGPT or Go to NetNinja YT
---
