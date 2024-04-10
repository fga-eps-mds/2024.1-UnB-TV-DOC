# Políticas de Contribuição

## 1. Introdução

Esse documento guia como devem ser feitas as contribuições no projeto. Ele se baseia nas [políticas do grupo do UnB-TV do semestre 2023.2](https://fga-eps-mds.github.io/2023.2-UnB-TV-DOC/#/./politicas/CONTRIBUTING), a fim de que o projeto continue tendo similaridades na parte de contribuição.

## 2. Guia de Contribuição

### 2.1. Reportar Bugs

Para reportar um Bug, uma issue deve ser criada seguindo o template abaixo:

```
# Nome do bug ou da melhoria a ser sugerida

## Descrição

Descrever o bug ou a melhoria breve e objetivamente

## Como reproduzir o Bug

Passo a passo detalhado de como o Bug pode ser encontrado/reproduzido

## Contexto adicional

Adicione comentários adicionais que considerar importante
```

### 2.2. Sugerir Melhorias

Para sugerir uma melhoria, uma issue deve ser criada seguindo o template abaixo:

```
# Nome da melhoria a ser sugerida

## Descrição

Descrever a melhoria breve e objetivamente

## Detalhamentos importantes da melhoria

Explicar de forma mais detalhada o que deve ser feito para a melhoria ser apresentada

## Contexto adicional

Adicione comentários adicionais que considerar importante
```

### 2.3. Branch

As novas branchs criadas devem seguir o padrão:

1. Toda nova branch deve ser feita a partir da develop;
2. Ao resolver a issue proposta, a nova branch deve ser incorporada por meio da solicitação de um Pull Request;
3. Caso o PR seja aprovado pela equipe, a nova branch será deletada;
4. Na develop será testada a integração entre as funcionalidades recentemente adicionadas;
5. Quando a equipe atestar a estabilidade da develop seu conteúdo é integrado a master.

A nome da branch deve ser associado ao número da issue e da tarefa, já que toda branch deve ter uma tarefa associada. Exemplo:

```
9-Nome-da-tarefa
```

### 2.4. Commit

Os commits devem ser atômicos (uma contribuição pequena para resolver um problema específico) e significativos. A mensagem do commit deve conter o que foi feito de maneira sucinta e direta, além disso ela precisa estar em **português**, **começar** com um **verbo** e com a **primeira letra maiúscula**. Exemplo de como um commit deve ser feito:

```
$ git commit -m "Adiciona estrutura inicial do documento de identidade visual"
```

Caso mais de uma pessoa tenha trabalhado no commit, a funcionalidade co-autoria deve ser feita, da seguinte maneira:

```
$ git commit -m "Cria model do usuário
>
>
Co-authored-by: name <name@example.com>
Co-authored-by: another-name <another-name@example.com>"
```

### 2.5. Pull Request

Ao criar um Pull Request, ele deve seguir o seguinte padrão:

1. Nome, deve ter o número e nome da issue: `# N° - Nome Issue`
2. Conteúdo, deve ser uma lista com principais modificações:

```
1. Descrição breve da issue
2. Issue Relacionada
3. Como Isso Foi Testado?
4. Capturas de Tela (se apropriado)
5. Tipos de Mudanças
```

3. Preencher os seguintes critérios de aceitação:

```
1. Testes criados.
2. Testes passando.
3. Build passando.
```

## 3. Versionamento do Documento

| Data | Versão | Descrição | Autor |
| :-----: | :-------------: | :---------------: | :-: |
| 31/03/2023 | 1.0 | Versão inicial com pontos 1 a 2 (2.5) | [Victor Hugo Oliveira Leão](https://github.com/victorleaoo) |
| 10/04/2024 | 1.1 | Ajuste na padronização do documento | [Gabriel Roger Amorim da Cruz](https://github.com/GabrielRoger07) |