# Criando banco de dados relacionais com Docker

## Criando um banco de dados Postgres
**Nas variáveis de ambiente do Postgres, definimos um único usuário com privilégios administrativos totais.**

`docker run -d -p 5432:5432 --name postgres-imobly -e POSTGRES_PASSWORD=root -e POSTGRES_USER=root -e POSTGRES_DB=database-imobly postgres:17`

* POSTGRES_USER: define o nome do usuário root.
* POSTGRES_PASSWORD: define a senha do usuário root.
* POSTGRES_DB: define o nome do banco de dados.

## Criando um banco de dados MariaDB
**Nas variáveis de ambiente do MariaDB/MySQL, definimos dois usuários (o comum/não root é opcional), um sendo o administrador máximo(root), enquanto o outro possui permissões administrativas apenas no banco de dados defindo no corrente comando.**

`docker run -d -p 3306:3306 --name mariadb-imobly -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=database_imobly -e MYSQL_USER=user -e MYSQL_PASSWORD=user mariadb:11`


* MYSQL_USER: define o nome do usuário comun/não root.
* MYSQL_PASSWORD: define a senha do usuário comum/não root.
* MYSQL_ROOT_PASSWORD: define a senha do usuário root.
* MYSQL_DATABASE: define o nome do banco de dados.
