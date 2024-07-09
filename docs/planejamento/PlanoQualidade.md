# Plano de Qualidade

## 1. Introdução

A qualidade de software pode ser definida como uma gestão de qualidade efetiva aplicada de modo a criar um produto útil que forneça valor mensurável para aqueles que o produzem e para aqueles que o utilizam. Neste documento, são apresentadas as ferramentas utilizadas para garantir a qualidade do projeto durante o seu desenvolvimento, além da análise de métricas para estabelecer critérios de qualidade.

## 2. Ferramentas

### 2.1 SonarCloud

O SonarCloud é uma ferramenta amplamente empregada para coletar métricas e indicadores técnicos, permitindo o monitoramento da qualidade do código. Durante o desenvolvimento do projeto, métricas seão capturadas após cada PR. Essas métricas foram combinadas para calcular os aspectos relevantes de qualidade do código, com foco na confiabilidade e manutenibilidade. Esses dados são cruciais para orientar o planejamento de melhorias contínuas, visando garantir um código confiável e de fácil manutenção.

### 2.2 Testes Unitários - Jasmine (Front End)

Jasmine é um framework open source para a realização de testes unitários a partir de códigos que utilizam da linguagem JavaScript. O Jasmine tem como característica a sua fácil utilização e a independencia de outros frameworks. No projeto utilizaremos o Jasmine para realizar testes no front-end.

A meta principal dos testes não é necessariamente provar a total correção de um software, mas identificar e corrigir defeitos potenciais. Apesar das limitações teóricas, é importante que cada comando no código seja examinado e que as atribuições de valor às variáveis sejam rigorosamente verificadas para garantir a funcionalidade e a confiabilidade do software em desenvolvimento. Os testes unitários são testes automatizados cujo objetivo é verificar o desempenho de partes isoladas de código em um sistema maior.

### 2.3 Testes Unitários - TestClient (Back End)

Ferramenta muito utilizada para testagem do framework FastAPI. Tem como característica ser de fácil utilização. Será usado pela equipe para a realização de testes unitários no back-end.

### 2.4 Testes Unitários - Pytest (Back End)

Para assegurar a qualidade e a robustez do sistema, a equipe empregou o Pytest no backend para a execução de testes unitários. O Pytest, uma ferramenta de teste unitário gratuita e de código aberto, é focado na comunidade e adequado para o desenvolvimento em Python. Ele é amplamente utilizado para testar código Python e é compatível com várias ferramentas e frameworks populares no ecossistema Python.

### 2.5 ESLint

O ESLint é uma ferramenta muito utilizada para fazer a verificação e análise estática de código JavaScript. Ela ajuda os desenvolvedores a garantir a qualidade do código, ao encontrar e relatar possíveis problemas, erros ou práticas inadequadas de programação. O ESLint disponibiliza várias regras configuráveis, que podem ser personalizadas de acordo com as necessidades do projeto, permitindo a aplicação de padrões de codificação consistentes e melhorando a legibilidade, a manutenibilidade e a interoperabilidade do código-fonte.

### 2.6 Verificação e Validação

A verificação e validação (V&V) são etapas cruciais para assegurar a funcionalidade e a adequação do produto às necessidades do cliente. A **verificação** se concentra em confirmar se o software realiza suas funções designadas corretamente, enquanto a **validação** verifica se o produto atende aos requisitos e expectativas do cliente.

Para garantir a qualidade do projeto, a equipe adotou as seguintes técnicas de verificação e validação:

**Validações com os donos do produto:** É essencial envolver os donos ou usuários do projeto na validação. Serão realizadas reuniões semanais com os POs para validar o progresso e obter feedback. Essa interação contínua ajuda a garantir que o software esteja sendo desenvolvido de acordo com as expectativas e necessidades dos stakeholders.

**Inspeção contínua do código:** A equipe optou por utilizar o Sonar Cloud como ferramenta de análise estática de código. Essa técnica permite obter métricas mensuráveis e identificar potenciais problemas no código-fonte. O Sonar Cloud fornece informações relevantes para a gestão da qualidade do projeto, auxiliando na tomada de decisões e na identificação de pontos que precisam ser aprimorados pela equipe.

**Testes automatizados**: Além da análise estática, a equipe utilizou testes automatizados, incluindo testes unitários e de integração, que atuam atuam durante o desenvolvimento e nas revisões de Pull Requests, para auxiliar no gerenciamento do projeto.

**Revisão de PRs:** Foi implementada uma prática de verificação de correção de PRs. Antes de mesclar um PR no repositório principal, algum membro da equipe de EPS revisa o código, analisando a lógica, a qualidade, a conformidade com as diretrizes do projeto e identificando possíveis melhorias ou problemas.

## 3. Métricas de qualidade

As métricas de qualidade definidas para o software são:

| Métrica          | Descrição                                     |
| ---------------- | --------------------------------------------- |
| Bugs             | Número de problemas identificados no código   |
| Coverage         | Grau de cobertura dos testes no código        |
| Duplicação       | Quantidade de linhas de código duplicadas     |
| Linhas           | Total de linhas de código no projeto          |
| Security Rating  | Avaliação de segurança e vulnerabilidades     |
| Complexidade  | Complexidade ciclomática. Define a complexidade de um programa. |
| Comentários  | Densidade (%) de linhas comentadas.     |

Através do uso de métricas, é possível identificar as subcaracterísticas relacionadas e avaliar a qualidade do produto. Essa avaliação fornece insights sobre a produtividade do projeto e influencia as decisões tomadas durante o desenvolvimento. Os valores mínimos aceitáveis para cada métrica do projeto foram estabelecidos com base nas métricas especificadas no SonarCloud.

| Métrica           | Critério                         |
| ----------------- | -------------------------------- |
| Bugs              | Classificado como "A"            |
| Coverage          | Pelo menos 90% de cobertura      |
| Duplication       | Até 3.0% de duplicação de código |
| Security Hotspots | Classificado como "A"            |
| Complexity       | Até 10 de complexidade |
| Comment Lines Density (%)       | Até 30% de densidade de comentários |

## 4. Referências

> Qualidade de Software. Disponível em: <https://www.devmedia.com.br/qualidade-de-software-engenharia-de-software-29/18209>. Acesso em 05 julho. 2024

> ISO/IEC 25010. ISO 25000. Software and data quality. 2011. Disponível em: <https://iso25000.com/index.php/en/iso-25000-standards/iso-25010>. Acesso em 04 julho. 2024

> ENGSOFTMODERNA. Engenharia de Software Moderna. Disponível em: <https://engsoftmoderna.info/>. Acesso em 04 julho. 2024

> PRESSMAN, Roger S.; MAXIM, Bruce R. Engenharia de software. Grupo A, 2021. E-book. ISBN 9786558040118. Disponível em: <https://integrada.minhabiblioteca.com.br/#/books/9786558040118/>. Acesso em 06 julho. 2024

> DELAMARO, Marcio. Introdução ao Teste de Software. Grupo GEN, 2016. E-book. ISBN 9788595155732. Disponível em: <https://integrada.minhabiblioteca.com.br/#/books/9788595155732/>. Acesso em 06 julho. 2024


##  5. Versionamento do Documento

| Data | Versão | Descrição | Autor |
| :-----: | :-------------: | :---------------: | :-: |
| 06/07/2024 | 1.0 | Versão inicial do documento | [Vinícius Assumpção de Araújo](https://github.com/viniman27) |
| 06/07/2024 | 1.1 | Correções estruturais | [Victor Hugo Oliveira Leão](https://github.com/victorleaoo) | 
| 09/07/2024 | 1.2 | Correções no padrão do documento | [Gabriel Roger Amorim da Cruz](https://github.com/GabrielRoger07) | 
