Docker is a containerization platform built on top of LXC.

Containers are like VMs in how you would use them. The difference is the VM hypervisor abstracts an entire machine.

Processes running within a container cannot see or affect any other container or the host system.

Docker is used to power microservice architecture. It's easier to maintain and update smaller applications and codebasse. It allows for faster release cycles by maintaining each service as an independent, stateless, highly available instance.

Basic Docker concepts
* `docker run --help` to view all commands
* Docker Daemon - Needs to be running on host for Docker to function. `docker ps` will list all containers. `docker ps -a` inspect all containers including in active
* Images - Root filesystem for Docker containers. Download one with `pull` keyword. E.g.: `docker pull busybox` List all images with `docker images`
* Container image registries - A runtime instance of a base image. E.g.:  `docker run busybox`

* Run shell command and enter container: `docker run -it busybox` use `exit` to leave the REPL.

* CMD - Every container has a default command whcih is run as the container is launched. Standard command structure: `docker run [OPTIONS] IMAGE [COMMAND] [ARG...]` example of passing commands: `docker run -it busybox ls -lh`

Remove container: `docker rm`
Name ontainer: `docker run -it --name hello busybox`


system port: 8080 port inside container: 80`docker run --name web -p 8080:80 nginx` accessible via docker at `localhost:8080`

run bash of container `docker exec -it web bash`

* Container Volumes