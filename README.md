### build image
docker build -t ast_tomcat -f tomcat/Dockerfile .
docker build -t ast_nginx -f nginx/Dockerfile .

### run
docker-compose up

### run in background (detached mode)
docker-compose up -d

### stop
docker-compose down

### list containers, images, volumes and networks
docker container ls
docker image ls
docker volume ls
docker network ls

### info
docker info

### cleanup
docker system prune

### get ip address of container
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' ast-tomcat-cluster

### get size of image
docker images
docker image inspect ast_nginx:latest --format='{{.Size}}'

### backup container
docker run --rm --volumes-from dbstore -v $(pwd):/backup ubuntu tar cvf /backup/backup.tar /dbdata

### bash into container
docker exec -it ast-nginx-portal bash

### get container logs
docker logs ast-nginx-portal

### get mounts of container
docker inspect -f '{{ .Mounts }}' ast-tomcat1

### copy file from container to host system
docker cp <containerId>:/file/path/within/container /host/path/target

