# Installing Docker

* Container engine
* microservices : database, server...


Installation :
```bash 
sudo apt install docker.io
```

Main docker cmd:
```bash 
docker
```

Look for alpine docker image:
```bash
docker pull alpine
```

How to run a new container:
```bash
docker run -di --name mycontainer alpine:latest
```

List of containers:
```bash
docker ps -a
```

Exec a sh in a container:
```bash
docker exec -ti mycontainer sh
```



More details : [docker hub](https://hub.docker.com)

    #docker
