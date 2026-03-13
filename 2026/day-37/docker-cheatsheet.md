


Docker Cheat Sheet
Container Commands
docker run [IMAGE]: Run a container from an image (e.g., docker run -d -p 80:80 nginx).

docker ps: List running containers (-a for all).

docker stop [ID/NAME]: Gracefully stop a container.

docker rm [ID/NAME]: Remove stopped container(s) (-f to force).

docker exec -it [ID/NAME] [CMD]: Run command in running container (e.g., /bin/bash).

docker logs [ID/NAME]: View container logs (-f to follow).

Image Commands
docker build -t [NAME:TAG] .: Build image from Dockerfile in current dir.

docker pull [IMAGE:TAG]: Download image from registry.

docker push [IMAGE:TAG]: Upload image to registry.

docker tag [SOURCE] [TARGET]: Create new tag for image.

docker images: List local images (-a for all, -q for IDs only).

docker rmi [IMAGE:TAG]: Remove image (-f to force).

Volume Commands
docker volume create [NAME]: Create a named volume.

docker volume ls: List all volumes.

docker volume inspect [NAME]: Show detailed volume info.

docker volume rm [NAME]: Remove volume (must be unused).

Network Commands
docker network create [NAME]: Create a network.

docker network ls: List all networks.

docker network inspect [NAME]: Show network details and connected containers.

docker network connect [NET] [CONTAINER]: Connect container to network.

Compose Commands
docker-compose up: Build/start services (-d detached, --build force rebuild).

docker-compose down: Stop and remove services (-v also remove volumes).

docker-compose ps: List services/containers.

docker-compose logs [SERVICE]: View service logs (-f follow).

docker-compose build: Build (or rebuild) services.

Cleanup Commands
docker system prune: Remove stopped containers, unused networks/images (-a all unused, -f no confirm).

docker system df: Show disk usage by images, containers, volumes.

Dockerfile Instructions
FROM [IMAGE:TAG]: Base image (e.g., FROM ubuntu:22.04).

RUN [CMD]: Execute command during build (chain with &&).

COPY [SRC] [DEST]: Copy files from host to image (or ADD for URLs/tars).

WORKDIR /path: Set working directory for next instructions.

EXPOSE [PORT]: Document exposed port (doesn't publish it).

CMD ["executable","param"]: Default command (overridden by docker run).

ENTRYPOINT ["executable","param"]: Executable on container start (append args).