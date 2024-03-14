# linux-tips-curso-docker

## Volumes

`docker volume ls`

`docker volume create teste`

`docker volume inspect teste`

`docker container run -it --mount type=volume,src=teste,dst=/giropops debian`