# linux-tips-curso-docker

## Criando uma imagem básica
`docker image build -t toskeira:1.0 .`

## Volumes

`docker volume ls`

`docker volume create teste`

`docker volume inspect teste`

`docker container run -it --mount type=volume,src=teste,dst=/giropops debian`

`docker volume rm teste`

`docker volume prune --all` https://github.com/docker/cli/issues/4028

Criar um volume

`docker volume create teste`

Subir dois serviços do postgres utilizando o volume

`docker run -d -p 5432:5432 --name pgsql1 --mount type=volume,src=teste,dst=/data -e POSTGRESQL_USER=docker -e POSTGRESQL_PASS=docker -e POSTGRESQL_DB=docker kamui/postgresql`

`docker run -d -p 5433:5432 --name pgsql2 --mount type=volume,src=teste,dst=/data -e POSTGRESQL_USER=docker -e POSTGRESQL_PASS=docker -e POSTGRESQL_DB=docker kamui/postgresql`

## Images

`docker commit -m "Ubuntu com vim e curl" 3da`

`docker image tag 0c4d48d615b2 ubuntu-with-vim-curl:1.0`