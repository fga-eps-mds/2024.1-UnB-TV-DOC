# Metodologias

## 1. Introdução

Esse documento apresenta as metodologias que serão trabalhadas pela equipe durante o desenvolvimento do projeto. Para cada uma delas, a equipe incorporou e decidiu algumas práticas a serem utilizadas. Dessa forma, para cada metodologia, será apresentada brevemente uma descrição dela e como serão aplicadas no projeto.

## 2. Metodologias

### 2.1. Scrum

Scrum é um framework dentro do qual pessoas podem tratar e resolver problemas complexos e adaptativos, enquanto produtiva e criativamente entregam produtos com o mais alto valor possível. Ele se baseia em ciclos curtos chamados sprints.

Dessa forma, as práticas aplicadas do Scrum pela equipe são:

1. **Sprints**: Ciclos de desenvolvimento, com tarefas bem definidas tendo início e fim.
2. **Estruturas de reuniões (Review, Planning e Daily)**: Podem ser encontradas no [plano de comunicação](./PlanoComunicacao.md).
3. **Backlog do Produto**: Artefato que contém a lista de requisitos (histórias de usuário) planejadas para o desenvolvimento do produto.
4. **Backlog da Sprint**: Artefato que contém a lista de histórias de usuário planejadas para o desenvolvimento no período de uma sprint.
5. **Papéis**: Os papéis de Scrum Master (facilitador) e Product Owner (dono do projeto), também, são acionados no projeto para poder estruturar melhor a equipe.

Além disso, o pensamento de metodologia ágil com entregas incrementais constantes irá guiar a equipe durante todo o desenvolvimento.

### 2.2. XP (Extreme Programming)

A Extreme Programming é uma metodologia de programação desenvolvida com a finalidade de otimizar as rotinas de times de desenvolvimento. O que abre espaço para que cada participante seja capaz de cumprir suas tarefas de um modo eficiente, sem gerar atrasos que possam encarecer o projeto.

Dessa forma, as práticas aplicadas da Extreme Programming pela equipe são:

1. **Programação em Pares**: Desenvolvedores trabalharão em pares para melhorar a qualidade do código e compartilhar conhecimento.
2. **Cliente Presente**: O cliente ou representante do cliente está envolvido no processo de desenvolvimento.
3. **Refatoração**: Processo de analisar um algoritmo pouco legível com a finalidade de simplificá-lo, facilitando a sua leitura. Será reforçado pela equipe.
4. **Testes Contínuos**: A cada mudança no código em repositório, os testes (build e deploy) são executados automaticamente para garantir a qualidade do código.
5. **Releases rápidas**: Iterações curtas que resultam em releases (entregas) frequentes.

### 2.3. Kanban

O Kanban é um sistema de organização e administração de projetos que visa controlar fluxos de maneira eficiente. Por ser altamente adaptável à realidade de diferentes negócios, o Kanban é um método amplamente adotado por setores que vão desde logística à desenvolvimento de software.

Para desenvolvimento de Software, as práticas aplicadas do Kanban pela equipe são:

1. **Quadro Kanban**: Um quadro visual que representa o fluxo de trabalho, com colunas que representam os estados das tarefas.
2. **Limites de Trabalho em Progresso (WIP)**: Restrições são aplicadas para controlar o número de tarefas em andamento em cada coluna.

Para o projeto, o quadro Kanban será feito e visualizado por meio da plataforma **Zenhub**. As seguintes colunas serão as presentes:

- **New Issues**: Para as tarefas no backlog do produto ainda não iniciadas.
- **Epics**: Para rastrear os grupos de tarefas que fazem parte dos objetivos de longo prazo, conceitos abragentes.
- **Icebox**: Para tarefas de prioridade baixa, que não precisam ser realizadas em um futuro próximo (desejos do cliente).
- **Product Backlog**: Para as tarefas planejadas para o produto durante o seu desenvolvimento atual.
- **Sprint Backlog**: Para as tarefas planejadas para a sprint.
- **In Progress**: Para as tarefas já iniciadas e em desenvolvimento na sprint (guiados pelo WIP).
- **Review/QA**: Tarefas da sprint em revisão para entrega.
- **Done**: Tarefas da sprint já concluídas.
- **Closed**: Para tarefas finalizadas, normalmente de sprints passadas já acabadas.

### 2.4. Lean Inception

O Lean Inception é um método de desenvolvimento de projetos ágeis que visa agilizar o processo de entrega do produto, garantindo maior assertividade e qualidade na sua entrega final.

Trabalha com o conceito de MVP (Produto Mínimo Viável): se refere a versão mais simples possível de um produto. Esta versão é utilizada como ferramenta principal na validação das premissas comerciais iniciais e/ou das expectativas colocadas no produto.

Dessa forma, a equipe aplicou o Lean Inception com o PO, com as seguintes etapas sendo evidenciadas:

- Visão do Produto;
- É, não é; faz, não faz;
- Objetivos do negócio;
- Personas;
- Jornada de usuário;
- Brainstorming de funcionalidades;
- Revisão técnica, de negócio e de UX;
- Sequenciador;
- Canvas MVP.

## 3. Referências

> Ken Schwaber & Jeff Sutherland: O Guia do Scrum. Disponível em: https://scrumguides.org/docs/scrumguide/v2020/2020-Scrum-Guide-Portuguese-European.pdf

> Cairo Noleto: Extreme Programming: o que é e quais as boas práticas?. Disponível em: https://blog.betrybe.com/carreira/extreme-programming/

> Wagner Hörlle: Lean Inception: O que é e como funciona esse método?. Disponível em: https://blog.csptecnologia.com/lean-inception/

## 4. Versionamento do Documento

| Data | Versão | Descrição | Autor |
| :-----: | :-------------: | :---------------: | :-: |
| 31/03/2024 | 1.0 | Versão inicial com pontos 1 a 3 | [Victor Hugo Oliveira Leão](https://github.com/victorleaoo) |
| 10/04/2024 | 1.1 | Ajuste na padronização do documento | [Gabriel Roger Amorim da Cruz](https://github.com/GabrielRoger07) |
