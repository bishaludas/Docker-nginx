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
