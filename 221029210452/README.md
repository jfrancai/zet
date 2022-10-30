# Mount a Persistent Volume

Start one or more stopped containers
> docker start

Stop one or more running containers
> docker stop

Remove one or more containers
> docker rm

Persistent volume:
> docker run -tid -p 8080:80 -v /srv/data/nginx:/usr/share/nginx/html --name web nginx:latest

    #docker
