# Docker
Setup a docker container with nginx and php-fpm

## Commands
- docker ps , lists docker process
- docker ps -a , lists docker containers
- docker images , lists docker images
- docker rm <process_id>, kill process
- docker rmi <imageid>, remove docker image
- docker run -it --rm <ubuntu> , run an image in interactive mode and remove it after closing
- docker run -p 9090:80 -v $PWD/file:/www/html nginx , commang for port mapping and volume mapping
- docker build -t namespace/appname:tagname -f path/to/docker/app/DockerFile docker/app/
	docker build -t namespace/appname:tagname -f ./DockerFile .
	```Build a container from docker file, tagname and path to Dockerfile```
- docker exec -it <image id><command : bash>
- Remove stopped containers : `docker rm $(docker ps -a -q)`

## Network command
- docker network -- help, help page
- docker network ls , lists the network
- docker network create <network_name>
- Run a container in network : --network=<network_name> 
- docker network inspect <network name>


## Postgres image
- docker run -d --rm --name=pgsql -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=homestead --network=timurnetwork postgres:latest

## Install and run laravel app in container
- docker run -it --rm -v $(pwd):/var/www/html -w /var/www/html timur/app:latest composer create-project laravel/laravel application
    ```or first clone laravel repo locally and volume map it into our custmo image"
- docker run --name=timurapp -d --rm --network=timurnetwork -p 9090:80 -v $PWD/application:/var/www/html timur/app


## Docker volumes
- docker volume ls
- docker volume create <volume name>
- docker run -d --rm --name=timurdb --network=timurnetwork -v timurbak:/var/lib/postgresql/data -e POSTGRES_PASSWORD=postgres  postgres


