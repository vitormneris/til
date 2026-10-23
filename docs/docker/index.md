# Principais comandos Docker


## Gerenciamento de containers

* **Lista todos os containers em estado running.**

`docker ps`

* **Lista todos os containers independente de estado.**

`docker ps -a`

* **Inicia um ou mais container(s) que já existe(m).**

`docker start CONTAINER_ID_OR_NAME`

* **Para um ou mais container(s) que está(ão) rodando.**

`docker stop CONTAINER_ID_OR_NAME`

* **Reinicia um container.**

`docker restart CONTAINER_ID_OR_NAME`

* **Remove/Apaga um ou mais container(s).**

`docker rm CONTAINER_ID_OR_NAME`

* **Renomeia um container.**

`docker rename OLD_CONTAINER_NAME NEW_CONTAINER_NAME` 


## Gerenciamento de imagens


* **Lista todas as imagens.**

`docker image ls` ou `docker images`

* **Remove/Apaga uma ou mais imagem(ns).**

`docker image rm IMAGE_ID_OR_NAME` ou `docker rmi IMAGE_ID_OR_NAME`

* **Baixar um imagem a partir de um repositório de imagens. Tag referece a versão.**

`docker image pull IMAGE_NAME:TAG`


## Gerenciamento de rede

* **Criar uma network.**

`docker network create`

* **Lista todas as networks.**

`docker network ls`

* **Conecta um container a uma network.**

`docker network connect NETWORK_NAME CONTAINER_ID_OR_NAME`

* **Disconecta um container de uma network.**

`docker network disconnect NETWORK_NAME CONTAINER_ID_OR_NAME`

* **Remove uma network.**

`docker network rm NETWORK_NAME`