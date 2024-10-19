# Docker Command Reference

This README provides an overview of essential Docker commands, covering clean-up operations, container interactions, container inspections, image management, registry interactions, and service management. It is a handy reference for anyone working with Docker to streamline development, deployment, and maintenance of containerized applications.

## Clean Up Commands
These commands help keep your Docker environment clean by removing unused containers, images, and volumes:

| Command | Explanation |
|---------|-------------|
| `docker image prune` | Clears unused images. |
| `docker image prune -a` | Clears all images that are not being used by containers. |
| `docker system prune` | Removes all stopped containers, all networks not used by containers, all dangling images, and build cache. |
| `docker image rm <image>` | Removes a specified image. |
| `docker rm <container>` | Removes a specified container. |
| `docker swarm leave` | Leaves a Docker swarm. |
| `docker stack rm <stackname>` | Removes a Docker stack. |
| `docker volume rm $(docker volume ls -f dangling=true -q)` | Removes all dangling volumes. |
| `docker rm $(docker ps -a -q)` | Removes all stopped containers. |
| `docker kill $(docker ps -q)` | Stops all running containers. |

## Container Interaction Commands
These commands are used to start, stop, and manage containers:

| Command | Explanation |
|---------|-------------|
| `docker start <container>` | Starts a new or stopped container. |
| `docker stop <container>` | Stops a running container. |
| `docker pause <container>` | Pauses a running container. |
| `docker unpause <container>` | Unpauses a paused container. |
| `docker restart <container>` | Restarts a running or stopped container. |
| `docker wait <container>` | Waits for a container to stop and returns its exit code. |
| `docker export <container>` | Exports the contents of a container to a tar archive. |
| `docker attach <container>` | Attaches to a running container. |
| `docker commit -m "commit message" -a "author" <container> <username/image_name>:<tag>` | Saves a running container as an image. |
| `docker logs -ft <container>` | Follows and displays logs of a container. |
| `docker exec -ti <container> <command>` | Runs a command inside a running container. |
| `docker create <image>` | Creates a new container from an image. |

## Container Inspection Commands
These commands provide insights into container statuses, logs, and running processes:

| Command | Explanation |
|---------|-------------|
| `docker ps` | Lists all running containers. |
| `docker ps -a` | Lists all containers, including stopped ones. |
| `docker diff <container>` | Shows changes made to files and directories in the container's filesystem. |
| `docker top <container>` | Displays processes running in a container. |
| `docker inspect <container>` | Shows detailed information about a container. |
| `docker logs <container>` | Retrieves logs of a container. |
| `docker stats <container>` | Displays resource usage statistics of a container. |

## Manage Images Commands
These commands help in managing Docker images:

| Command | Explanation |
|---------|-------------|
| `docker image ls` | Lists all Docker images. |
| `docker image rm <image>` | Removes a specified Docker image. |
| `docker tag <image> <tag>` | Assigns a tag to an image for easier reference. |
| `docker history <image>` | Shows the history of changes for an image. |
| `docker inspect <image>` | Displays detailed information about an image. |

## Registry Commands
Manage Docker images in registries like Docker Hub:

| Command | Explanation |
|---------|-------------|
| `docker login` | Logs in to a Docker registry. |
| `docker logout` | Logs out from a Docker registry. |
| `docker pull <image>` | Pulls an image from a registry. |
| `docker push <repo>/<image>:<tag>` | Pushes an image to a registry. |
| `docker search <term>` | Searches Docker Hub for images containing the specified term. |

## Service Commands
Manage Docker services within a swarm environment:

| Command | Explanation |
|---------|-------------|
| `docker service ls` | Lists all services running in a Docker swarm. |
| `docker stack services <stackname>` | Lists all services in a specific stack. |
| `docker service ps <servicename>` | Lists the tasks of a specified service. |
| `docker service update <servicename>` | Updates a running service. |
| `docker service create <image>` | Creates a new service from an image. |
| `docker service scale <servicename>=<replicas>` | Scales the specified service to a desired number of replicas. |

## Run Commands
Create containers from images using the `docker run` command:

| Command | Explanation |
|---------|-------------|
| `docker run (options) <image> (command) (arg...)` | Creates and runs a container from an image. |

### Common Options:
- `-d` / `--detach`: Run the container in the background.
- `-e` / `--env`: Set environment variables.
- `-h` / `--hostname`: Set the container's hostname.
- `-l` / `--label`: Add metadata labels.
- `--name`: Assign a name to the container.
- `--rm`: Remove the container automatically after it exits.
- `-w` / `--workdir`: Set the working directory inside the container.

This cheat sheet should help you quickly reference Docker commands to streamline your container management. For more detailed explanations, consult the Docker documentation: https://docs.docker.com/
