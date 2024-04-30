# Documentação dos Endpoints

## 1. Introdução

Esse documento apresenta a documentação de cada um dos endpoints do código fonte. Eles serão divididos pelos módulos (Users, Admin, VideoService e Gateway), e destrinchados em **url**, **método**, **descrição**, **dados de input/requisição** (caso tenha), **status** e **resposta**. As possibilidades de exceções também serão explicadas.


## 2. Endpoints de [Users](https://github.com/fga-eps-mds/2024.1-UnB-TV-Users)

### authController

1. get_connection: */auth/vinculo* => **GET**
    - **Descrição**:
        - Retorna os vínculos possíveis.
    - **Input/Requisição**: 
        - None
    - **Status**: 
        - 200 (OK)
    - **Resposta**:
        - Lista de vínculos (em utils/enumeration.py)

2. register: */auth/register* => **POST**
    - **Descrição**:
        - Registra um usuário.
    - **Input/Requisição**:
        - UserCreate (domain/authSchema.py): name; connection; email; password.
    - **Status**: 
        - 201 (CREATED)
    - **Resposta**: 
        - Mensagem de sucesso
    - **Exceções**:
        - **INVALID_CONNECTION**: connection não for válido;
        - **INVALID_PASSWORD**: senha não for válida;
        - **EMAIL_ALREADY_REGISTERED**: e-mail já registrado.

3. login: */auth/login* => **POST**
    - **Descrição**:
        - Faz o login de um usuário.
    - **Input/Requisição**:
        - UserLogin (domain/authSchema.py): email; password.
    - **Status**: 
        - 200 (OK)
    - **Resposta**: 
        - access_token; 
        - refresh_token;
        - token_type: bearer.
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir;
        - **PASSWORD_NO_MATCH**: senha não for a do usuário;
        - **ACCOUNT_IS_NOT_ACTIVE**: conta não ativa.

4. login_social: */auth/login/social* => **POST**
    - **Descrição**:
        - Faz o login de um usuário por meio de uma rede social.
    - **Input/Requisição**:
        - UserSocial (domain/authSchema.py): name; email.
    - **Status**: 
        - 200 (OK)
    - **Resposta**: 
        - access_token; refresh_token; token_type: bearer; is_new_user; user_id.

5. refresh_token: */auth/refresh* => **POST**
    - **Descrição**:
        - Cria um novo token para um usuário logado.
    - **Input/Requisição**:
        - token
    - **Status**: 
        - 201 (OK)
    - **Resposta**: 
        - access_token; 
        - token_type: bearer.

6. send_new_code: */auth/resend-code* => **POST**
    - **Descrição**:
        - Envia novo código de verificação para um usuário.
    - **Input/Requisição**:
        - SendNewCode (domain/authSchema.py): email.
    - **Status**: 
        - 201 (CREATED)
    - **Resposta**: 
        - Mensagem de sucesso
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir;
        - **ACCOUNT_ALREADY_ACTIVE**: conta já estar ativa.

7. validate_account: */auth/activate-account* => **PATCH**
    - **Descrição**:
        - Valida a conta pelo código.
    - **Input/Requisição**:
        - AccountValidation (domain/authSchema.py): email; code.
    - **Status**: 
        - 200 (OK)
    - **Resposta**: 
        - Mensagem de sucesso
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir;
        - **ACCOUNT_ALREADY_ACTIVE**: conta já estar ativa;
        - **INVALID_CODE**: código de ativação não válido.

8. request_password_: */auth/reset-password/request* => **POST**
    - **Descrição**:
        - Solicitação de nova senha.
    - **Input/Requisição**:
        - ResetPasswordRequest (domain/authSchema.py): email.
    - **Status**: 
        - 200 (OK)
    - **Resposta**: 
        - Mensagem de sucesso
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir;
        - **ACCOUNT_IS_NOT_ACTIVE**: conta não ativa.

9. verify_reset_code: */auth/reset-password/verify* => **POST**
    - **Descrição**:
        - Verifica o código para resetar senha.
    - **Input/Requisição**:
        - ResetPasswordVerify (domain/authSchema.py): email; code.
    - **Status**: 
        - 200 (OK)
    - **Resposta**: 
        - Mensagem de sucesso
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir;
        - **NO_RESET_PASSWORD_CODE**: não haver código de resetar senha;
        - **INVALID_RESET_PASSWORD_CODE**: código de resetar senha inválido.

10. update_user_password: */auth/reset-password/change* => **PATCH**
    - **Descrição**:
        - Atualiza a senha de um usuário.
    - **Input/Requisição**:
        - ResetPasswordUpdate (domain/authSchema.py): email; password; code.
    - **Status**: 
        - None
    - **Resposta**: 
        - Usuário com senha atualizada
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir;
        - **INVALID_PASSWORD**: senha não válida;
        - **INVALID_REQUEST**: usuário não tem um código de resetar senha;
        - **INVALID_RESET_PASSWORD_CODE**: código de resetar senha inválido.

### userController

1. read_users: */users/* => **GET**
    - **Descrição**:
        - Retorna todos os usuários cadastrado.
    - **Input/Requisição**:
        - None
    - **Status**: 
        - None
    - **Resposta**: 
        - Lista de usuários.

2. read_user: */users/{user_id}* => **GET**
    - **Descrição**:
        - Retorna um usuário pelo id.
    - **Input/Requisição**:
        - user_id;
        - token.
    - **Status**: 
        - None
    - **Resposta**: 
        - Usuário com id do parâmetro
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir.

3. read_user_by_email: */users/email/{user_email}* => **GET**
    - **Descrição**:
        - Retorna um usuário por email.
    - **Input/Requisição**:
        - user_email;
        - token.
    - **Status**: 
        - None
    - **Resposta**: 
        - Usuário com email do parâmetro.
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir.

4. partial_update_user: */users/{user_id}* => **PATCH**
    - **Descrição**:
        - Atualiza os dados de um usuário.
    - **Input/Requisição**:
        - user_id;
        - token;
        - UserUpdate (domain/userSchema.py): name; email; connection.
    - **Status**: 
        - None
    - **Resposta**: 
        - Usuário atualizado.
    - **Exceções**:
        - **INVALID_CONNECTION**: vínculo não válido;
        - **USER_NOT_FOUND**: usuário não existir;
        - **EMAIL_ALREADY_REGISTERED**: email já registrado.

5. delete_user: */users/{user_id}* => **DELETE**
    - **Descrição**:
        - Deleta um usuário.
    - **Input/Requisição**:
        - user_id;
        - token.
    - **Status**: 
        - None
    - **Resposta**: 
        - Usuário deletado.
    - **Exceções**:
        - **USER_NOT_FOUND**: usuário não existir.

6. update_role: */users/role/{user_id}* => **PATCH**
    - **Descrição**:
        - Atualiza o papel de um usuário (admin, user).
    - **Input/Requisição**:
        - user_id;
        - token.
    - **Status**: 
        - None
    - **Resposta**: 
        - Usuário.
    - **Exceções**:
        - **NO_PERMISSION**: usuário sem permissão (não ser admin);
        - **USER_NOT_FOUND**: usuário não existir.

## 3. Endpoints de [Admin](https://github.com/fga-eps-mds/2024.1-UnB-TV-Admin/tree/develop)

### pautaController

1. simple_send: */pauta/email* => **POST**
    - **Descrição**:
        - Envia email com uma sugestão de pauta.
    - **Input/Requisição**: 
        - email (domain/pautaSchema.py): tema; descrição; quando; local; responsavel; telefone_responsavel; email_contato.
    - **Status**: 
        - 200 (OK)
    - **Resposta**:
        - Mensagem de sucesso

## 4. Endpoints de [VideoService](https://github.com/fga-eps-mds/2024.1-UnB-TV-VideoService/tree/develop)

### scheduleController

1. get_schedule_day: */schedule/* => **GET**
    - **Descrição**:
        - Realiza webscraping para obter o cronograma de eventos.
    - **Input/Requisição**: 
        - day (opcional).
    - **Status**: 
        - None.
    - **Resposta**:
        - Cronograma
    - **Exceções**:
        - **INVALID_SCHEDULE_DAY**: dia passado for inválido;
        - **ERROR_RETRIEVING_SCHEDULE**: erro ao obter o cronograma.

## 5. Versionamento do Documento

| Data | Versão | Descrição | Autor |
| :-----: | :-------------: | :---------------: | :-: |
| 20/04/2023 | 1.0 | Versão inicial com pontos 1 a 5 | [Victor Hugo Oliveira Leão](https://github.com/victorleaoo) |