--> Override entrypoint
docker run -it --entrypoint /bin/bash [docker_image]

--> Stop and remove all containers
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)

--> List all volumes
docker volume ls

--> Remove all dangling volumes
docker volume rm $(docker volume ls -f dangling=true -q)


--> remove all unused networks
docker network prune

--> remove all stopped containers
docker container prune

--> remove all unused local volumes
docker container prune

--> remove all unused networks, containers, volumes and dangling images
docker system prune

--> remove everything except runned
docker system prune -a

--> get container ip address
docker container inspect --format '{{ .NetworkSettings.IPAddress }}' cnt_name