# Documento de Arquitetura

## 1. Introdução

Este documento detalha a estrutura do software de um projeto que incorpora Angular para o frontend. Ele é composto por quatro microsserviços desenvolvidos com FastAPI, um gateway em Node para facilitar a comunicação entre esses serviços e um banco de dados PostgreSQL, além de consumir a API do EduPlay para acessar os vídeos e programas ao vivo. A estrutura projetada tem foco na escalabilidade, resiliência e alto desempenho. Baseia-se no conceito de microsserviços, onde componentes distintos funcionam como serviços autônomos, interagindo por meio de interfaces claramente estabelecidas. Este é um esboço da arquitetura em um nível geral:

<p align="center">
    <img src="https://raw.githubusercontent.com/fga-eps-mds/2024.1-UnB-TV-DOC/main/docs/assets/arquitetura.png" />
</p>
<p align="center">
Fonte: Adaptado do semestre anterior
</p>

## 2. Tecnologias

### 2.1. Angular

Angular é empregado como a principal tecnologia de frontend neste projeto, proporcionando uma interface de usuário interativa e responsiva. Sua arquitetura robusta e recursos avançados de bidirectional data binding facilitam a gestão eficiente dos estados da interface, enquanto sua integração com os microsserviços via HTTP garante uma comunicação fluida e eficiente. Angular também contribui para uma manutenção mais fácil e um desenvolvimento ágil, graças à sua estrutura modular e ao extenso ecossistema de ferramentas.

### 2.2. FastAPI

FastAPI é utilizado neste projeto para desenvolver três microsserviços, destacando-se por sua alta performance e facilidade de uso. Este framework de Python permite a construção rápida de APIs eficientes, com recursos automáticos de documentação interativa e validação de dados. A escolha do FastAPI apoia a arquitetura de microsserviços do projeto, proporcionando uma comunicação ágil e confiável entre os diferentes serviços, além de facilitar a escalabilidade e manutenção do sistema.

### 2.3. Node.js


Node.js é um ambiente de execução JavaScript usado no projeto para a construção do gateway, devido ao seu desempenho assíncrono e não bloqueante, permitindo a gestão eficiente de múltiplas conexões simultâneas. Também se adapta bem a arquiteturas de microsserviços e é multiplataforma, facilitando a implantação em diferentes sistemas operacionais, o que torna esta tecnologia uma escolha robusta e versátil para o gateway.

### 2.4. PostgreSQL

No projeto, o PostgreSQL é utilizado como o sistema de gerenciamento de banco de dados, oferecendo uma solução robusta e confiável para armazenamento e recuperação de dados. Sua escolha deve-se à sua performance elevada, suporte a transações complexas e compatibilidade com os padrões SQL. Além disso, o PostgreSQL é conhecido por sua extensibilidade e forte conformidade com ACID, garantindo a integridade e a segurança dos dados. Essas características o tornam uma escolha adequada para gerenciar as informações críticas e assegurar a eficiência na manipulação de dados no contexto do projeto.

## 3. Representação dos serviços

-   **Frontend:** Responsável por todas as interações do usuário com o sistema, este serviço é o meio pelo qual o usuário pode acessar visualmente as funcionalidades oferecidas no contexto da aplicação. Exemplo: Logar por redes sociais ou email, visualizar o católogo dos vídeos com os programas, sugerir pauta, assistir ao canal ao vivo.

-   **VideoService:** Microserviço responsável pelas interações entre usuário e vídeo, além do módulo de recomendações. Também é responsável pela grade de programação dos programas (a funcionalidade de comentários foi retirada).

-   **Users:** Microsserviço responsável pela gestão dos usuários da aplicação.

-   **Admin:** Microsserviço responsável pela conta do admin, como delegar admin a outros usuários, receber as pautas sugeridas, gerar notificações para a aplicação.

-   **Gateway:** Responsável para realizar a interface do usuário com os demais serviços da aplicação, provendo autenticação e autorização.

## 4. Visão lógica

Composto por dois tipos de diagramas:

- **Diagrama de pacotes:** organizar elementos do sistema em grupos chamados pacotes. Esses pacotes representam agrupamentos lógicos de classes, interfaces e outros elementos que compartilham um propósito comum. O diagrama de pacotes ajuda a visualizar a estrutura de alto nível do sistema, mostrando como os pacotes estão relacionados e como eles dependem uns dos outros, facilitando a compreensão da organização e modularidade do sistema.
- **Diagrama de implantação:** ilustrar a configuração física de hardware e software do sistema. O diagrama de implantação ajuda a entender como o sistema será fisicamente distribuído, como os componentes se comunicam entre si e quais recursos de hardware são necessários, permitindo uma visão clara da arquitetura física e dos requisitos de infraestrutura do sistema.

### 4.1. Diagrama de pacote Front-end

<p align="center">
    <img src="https://raw.githubusercontent.com/fga-eps-mds/2024.1-UnB-TV-DOC/4e5aa4f32aa3d5d998de12b0750103d99f877e4b/docs/assets/frontend.svg" />
</p>

### 4.2. Diagrama de pacote Back-end

<p align="center">
    <img src="https://raw.githubusercontent.com/fga-eps-mds/2024.1-UnB-TV-DOC/4e5aa4f32aa3d5d998de12b0750103d99f877e4b/docs/assets/backend.svg" />
</p>

### 4.3. Diagrama de implantação

<p align="center">
    <img src="https://raw.githubusercontent.com/fga-eps-mds/2024.1-UnB-TV-DOC/main/docs/assets/implantacao.png" />
</p>

## 5. Diagrama Entidade Relacionamento (DER)

O diagrama de entidade-relacionamento serve como uma ferramenta gráfica para modelar bancos de dados, proporcionando uma visão clara e abrangente da estrutura do banco de dados. Este diagrama é útil para equipes de desenvolvimento, pois descreve visualmente os objetos (entidades) que fazem parte do projeto, incluindo suas características específicas (atributos) e as formas como se relacionam entre si.

![Diagrama Entidade Relacionamento](doc/assets/DER.png)


## 6. Diagrama Lógico de Dados (DLD)

O diagrama lógico de dados é uma representação detalhada que se aproxima da estrutura final a ser implementada no banco de dados. Este diagrama inclui tabelas, especificando todos os atributos, além de identificar as chaves primárias e estrangeiras. Ele define a estrutura dos elementos de dados e seus inter-relacionamentos, descrevendo assim as necessidades de dados requeridas para o projeto.

![Diagrama Lógico de Dados](doc/assets/Lógico.png)

## 5. Referências Bibliográficas

CREATELY. O Guia Fácil de Diagramas de Implantação UML. Disponível em: https://creately.com/blog/pt/diagrama/tutorial-do-diagrama-de-implantacao.

Geekhunter. O que são microsserviços e como funcionam?. Disponível em: https://blog.geekhunter.com.br/arquitetura-de-microsservicos-x-arquitetura-monolitica/.

## 6. Histórico de versão

| **Data**   | **Descrição**                                    | **Autore(es)**    |
| ---------- | ------------------------------------------------ | ----------------- |
| 15/07/2024 | Adição inicial do documento                              | [Vinícius Assumpção de araújo](https://github.com/viniman27)          |
| 16/07/2023 | Adição do diagrama de arquitetura e implantação | [Victor Hugo Oliveira Leão](https://github.com/victorleaoo) |
