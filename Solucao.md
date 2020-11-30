# Containerização

Foram utilizados Docker e Docker-compose para a Containerização e orquestração da aplicação.

Obs.: Os comandos abaixo devem ser utilizados a partir da raiz do projeto

### Para rodar somente o client

```bash
docker build -t vue-app ./client
docker run -p 8080:8080 vue-app
```

### Para rodar somente a api com o banco

```bash
docker-compose -f ./api/docker-compose.yml up --build
```

### Para rodar somente a api com o banco

```bash
docker-compose up --build
```

## Configuração do Banco

Caso seja a primeira vez que o projeto esteja sendo rodado, o banco deve ser criado utilizando o seguinte comando:

```bash
docker-compose run api rake db:create
```

Caso o banco precise de migração rode o seguinte comando:

```bash
docker-compose run api rake db:migrate
```