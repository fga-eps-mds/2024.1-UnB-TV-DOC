# Documentação dos Endpoints

## 1. Introdução

Esse documento apresenta a documentação de cada um dos endpoints do código fonte. Eles serão divididos pelos módulos (Users, Admin, VideoService e Gateway), e destrinchados em **url**, **método**, **dados de input/requisição** (caso tenha), **status** e **resposta**. As possibilidades de exceções também serão explicadas.


## 2. Endpoints de user

### authController

1. get_connection: */auth/vinculo* => **GET**
    - **Input/Requisição**: 
        - None
    - **Status**: 
        - 200 (OK)
    - **Resposta**:
        - Lista de vínculos (em utils/enumeration.py)

2. register: */auth/register* => **POST**
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
    - **Input/Requisição**:
        - UserSocial (domain/authSchema.py): name; email.
    - **Status**: 
        - 200 (OK)
    - **Resposta**: 
        - access_token; refresh_token; token_type: bearer; is_new_user; user_id.

5. refresh_token: */auth/refresh* => **POST**
    - **Input/Requisição**:
        - token
    - **Status**: 
        - 201 (OK)
    - **Resposta**: 
        - access_token; 
        - token_type: bearer.

6. send_new_code: */auth/resend-code* => **POST**
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
    - **Input/Requisição**:
        - None
    - **Status**: 
        - None
    - **Resposta**: 
        - Lista de usuários.

2. read_user: */users/{user_id}* => **GET**
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