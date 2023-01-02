# Projeto Baseado em Cliente Servidor no docker

[Frontend](https://hub.docker.com/repository/docker/amatheuslp/frontend-test)
[Backend](https://hub.docker.com/repository/docker/amatheuslp/backend-test)

# Executar em desenvolvimento

## Pré requisitos
- **Necessário a instalação do** [**Docker**](https://hub.docker.com/repository/docker/amatheuslp/backend-test) 
- **Necessário a instalaçao do Docker Compose**

## Passos

>$ docker-compose up

após isso é possivel acessar o frontend em **http://localhost:8080/**  e o backend em **http://localhost:3000/**

# Executar em produção

## Pré requisitos
- **Necessário a instalação do** [**Docker**](https://hub.docker.com/repository/docker/amatheuslp/backend-test) 
- **Necessário a instalaçao do Docker Compose**

## Passos

- Criar o arquivo docker-compose.yml
```
version:  '3'
services:
	db:
		image:  mongo:3.4
	backend:
		image:  amatheuslp/backend-test:1.1
		depends_on:
			-  db
		ports:
			-  3000:3000
	frontend:
		image:  amatheuslp/frontend-test:1.0
		ports:
			-  8080:80
```

- Executar o comando
>$ docker-compose up

após isso é possivel acessar o frontend em **http://localhost:8080/**  e o backend em **http://localhost:3000/**