# Como Rodar o Projeto Localmente

## 1. Introdução

Esse é um tutorial com passo a passo de como rodar o projeto localmente para os desenvolvedores. Basicamente, todos os módulos do projeto possuem um Docker para tornar possível o deploy local, mas, também, configurações individuais.

**Importante**: os arquivos .env tem atributos entre {}, quer dizer que eles são confidenciais, logo devem ser obtidos de forma própria, caso não seja integrante da disciplina no semestre. Caso seja, entre em contato com um estudante de EPS.

## 2. Módulo Users

Passo a Passo:

1. Em uma pasta, faça o clone do repositório: `git clone git@github.com:fga-eps-mds/2024.1-UnB-TV-Users.git` e entre na pasta do repositório: `cd 2024.1-UnB-TV-Users/`;
2. Crie um arquivo .env com o seguinte conteúdo:

```
SECRET={secret_alg}
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=999999

MAIL_USERNAME={email}
MAIL_PASSWORD={email_password}
MAIL_FROM={email}
MAIL_PORT={email_port}
MAIL_SERVER=smtp.gmail.com

CLIENT_ID={google_client_id}
CLIENT_SECRET={google_client_secret_id}

FACEBOOK_CLIENT_ID={facebook_client_id}
FACEBOOK_CLIENT_SECRET={facebook_client_secret_id}

POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_HOST=localhost
POSTGRES_DB=unbtv
```

3. Rode o Docker: `docker compose up --build`
4. Confira se a aplicação subiu em: *localhost:8000*.

## 3. Módulo Admin

1. Em uma pasta, faça o clone do repositório: `git clone git@github.com:fga-eps-mds/2024.1-UnB-TV-Admin.git` e entre na pasta do repositório: `cd 2024.1-UnB-TV-Admin/`;
2. Crie um arquivo .env com o seguinte conteúdo:

```
MAIL_USERNAME={email}
MAIL_PASSWORD={email_password}
MAIL_FROM={email}
MAIL_PORT={email_port}
MAIL_SERVER=smtp.gmail.com
```

3. Rode o Docker: `docker compose up --build`
4. Confira se a aplicação subiu em: *localhost:8080*.

## 4. Módulo VideoService

1. Em uma pasta, faça o clone do repositório: `git clone git@github.com:fga-eps-mds/2024.1-UnB-TV-VideoService.git` e entre na pasta do repositório: `cd 2024.1-UnB-TV-VideoService/`;
2. Crie um arquivo .env com o seguinte conteúdo:

```
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
POSTGRES_HOST=db
POSTGRES_DB=videos_db
POSTGRES_PORT=5432
```

3. Rode o Docker: `docker compose up --build`
4. Confira se a aplicação subiu em: *localhost:8001*.

## 5. Módulo FrontEnd

1. Em uma pasta, faça o clone do repositório: `git clone git@github.com:fga-eps-mds/2024.1-UnB-TV-Frontend.git` e entre na pasta do repositório: `cd 2024.1-UnB-TV-Frontend/`;
2. Crie um arquivo .env com o seguinte conteúdo:

```
videoAPIURL="http://localhost:8001/api"
usersAPIURL="http://localhost:8000/api"
adminAPIURL="http://localhost:8080/api"

EDUPLAY_CLIENT_KEY={eduplay_token}
```

3. Rode o Docker: `docker compose up --build`
4. Confira se a aplicação subiu em: *localhost:4200*.

## 6. Dicas

Comandos para limpar o Docker, interessante de usar caso enfrente algum erro:

- ```docker rm -vf $(docker ps -aq)```
- ```docker rmi -f $(docker images -aq)```

## 7. Versionamento do Documento

| Data | Versão | Descrição | Autor |
| :-----: | :-------------: | :---------------: | :-: |
| 15/07/2024 | 1.0 | Versão inicial com pontos 1 a 6 | [Victor Hugo Oliveira Leão](https://github.com/victorleaoo) |
