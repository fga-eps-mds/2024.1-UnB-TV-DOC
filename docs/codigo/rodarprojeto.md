# Como Rodar o Projeto Localmente

## 1. Introdução

Esse é um tutorial com passo a passo de como rodar o projeto localmente para os desenvolvedores. Basicamente, todos os módulos do projeto possuem um Docker para tornar possível o deploy local, mas, também, configurações individuais.

**Importante**: os arquivos .env tem atributos entre {}, quer dizer que eles são confidenciais, logo devem ser obtidos de forma própria, caso não seja integrante da disciplina no semestre. Caso seja, olhe o discord, pois lá serão postados os arquivos .env com os conteúdos.

## 2. Módulo Users

Passo a Passo:

1. Em uma pasta, faça o clone do repositório: `git clone git@github.com:fga-eps-mds/2024.1-UnB-TV-Users.git` e entre na pasta do repositório: `cd 2024.1-UnB-TV-Users/`;
2. Crie um arquivo .env com o seguinte conteúdo:

```
SECRET=sH8kBipqhPYcb!XN3MfVZcP2eVarfrj$xwBdfvZaXFKHQSSt
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
2. Atualize a seguinte dependência no arquivo *package.json*: `"@abacritt/angularx-social-login": "^1.0.0"`;
3. Rode o Docker: `docker compose up --build`
4. Confira se a aplicação subiu em: *localhost:8001*.