# Installing Docker

* Container engine
* microservices : database, server...


Installation :
> sudo apt install docker.io

Main docker cmd:
> docker

Look for alpine docker image:
> docker pull alpine

How to run a new container:
> docker run -di --name mycontainer alpine:latest

List of containers:
> docker ps -a

Exec a sh in a container:
> docker exec -ti mycontainer sh



More details : [docker hub](https://hub.docker.com)

    #docker
