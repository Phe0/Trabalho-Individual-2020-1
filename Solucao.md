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

# Integração Contínua

Foras utilizadas as ferramentas:
 - Github actions
 - SonarCloud

Afim de de realizar a integração contínua do projeto. O CI é responsável por realizar dois jobs, um para o client e outro para a api. Em cada um deles, são realizadas três etapas: build, teste, coleta de métricas.

Para a etapa de build é realizado o build do container docker.
Para a etapa de testes é realizado o comando de testes dentro do container.
Para a etapa de coleta de métricas é enviado um aviso para que o SonarCloud colete as métricas do projeto, ficando disponíveis [aqui](https://sonarcloud.io/dashboard?id=Phe0_Trabalho-Individual-2020-1).
