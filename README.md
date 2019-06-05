# build image
docker build -t ast_tomcat .
docker build -t ast_nginx .

# run
docker-compose up

# list containers, images, volumes and networks
docker container ls
docker image ls
docker volume ls
docker network ls

# info
docker info

# cleanup
docker system prune

# get ip address of container
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' ast-tomcat-cluster
