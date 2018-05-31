# Git

## Fluxo Git

O fluxo recomendado é um simples modelo de feature branch, com as seguintes características:

1. O master sempre está num estado deployable, ou seja, pode ir para produção
2. Todas as mudanças são feitas através de pull requests + merge, por meio da crianção de features branches. Os commits direto na master estão desabilitados
3. Para resolver conflitos e atualizar com a master, use rebase na sua feature branch

![](assets/images/git/feature-branches.svg)

Com base nele, o fluxo de desenvolvimento de uma nova funcionalidade seguiria os seguintes passos:

1. Dev: cria uma nova branch feat/[nome da feature]
2. Dev: durante o desenvolvimento ira realizar commits na branch criada
3. Dev: gera builds da feature branch conforme necessidade (ambiente de integração do dev)
4. Dev: ao término do desenvolvimento da feat, irá fazer git rebase master, para atualizar com o estado mais atual da branch de master, e assim já resolver possíveis conflitos
5. Dev: ira fazer o push da branch e criar um PR no Bitbucket para a branch master, colocando como reviewers a equipe de QA
6. Time: irá analisar o código, e uma vez que não sejam encontrados problemas, irá aprovar
7. Dev: após o PR aprovado, irá fazer o merge via interface do Bitbucket
8. Jenkins: gera o build da master para o ambiente de homologação
9. Dev: gera uma tag baseado na master, seguindo o padrão SEMVER, e faz o push para o Bitbucket git push --tags
10. Dev: promove a tag para produção através do Jenkins

![](assets/images/git/hotfix-branches.svg)

Agora em caso de hot-fix para produção. O fluxo seria o seguinte:

1. Dev: faz o checkout da versão de produção, utilizando tag git checkout v0.12.2
2. Dev: cria uma nova branch a partir da tag git checkout -b hotfix-v0.12.3-[Identificador do card no Trello]
3. Dev: faz o commit da fix
4. Dev: gera builds da hotfix conforme necessidade (ambiente de integração do dev)
5. Dev: faz o push da branch para o remote: git push -u origin hotfix-v0.12.3-[Identificador do card no Trello]
6. Dev: gera o build da branch de hotfix para o ambiente de homologação
7. Dev: uma vez validado o hotfix, o dev gera uma tag baseado na hotfix, seguindo o padrão SEMVER, e faz o push para o Bitbucket git push --tags
8. Dev: promove a tag para produção através do Jenkins
9. Dev: uma vez o hotfix aplicado e validado em prod, faz o PR para a master e a partir daqui segue o mesmo fluxo de uma feature (continuando do passo 5)

## Definições de nomenclatura
Os nomes dos branches criados devem seguir o seguinte padrão de nomenclatura:

```
tipo/TRELLO-CARD-ID
```

Onde o tipo deve se relacionar ao que aquela branch busca resolver, por exemplo, se será desenvolvida uma funcionalidade nova, se será implementada uma correção, etc.

Alguns tipos possíveis são os seguintes:

* feat (será implementada uma nova funcionalidade)
* fix (será implementada uma correção para resolver um problema existente)
* refactor (será realizado algum refactor em parte do código que já funciona)
* chore (será implementa alguma melhoria de código e/ou infraestrutura)
* test (será desenvolvido algum novo cenário de teste para a aplicação)
* docs (será feita alguma mudança na documentação)

Já no TRELLO-CARD-ID deve ser descrito o id do card para aquela história no JIRA do projeto.

Exemplos:

* feat/BOARD-1 - Nessa branch fica claro que está sendo desenvolvida uma nova funcionalidade e que ela se refere a história BOARD-1
* fix/BOARD-2 - Nessa branch também fica claro que está sendo realizada uma correção no que se refere a história BOARD-2

### Mensagens de commit
Para as mensagens de commit também deve-se seguir o seguinte esquema de nomenclatura:

```
tipo(TRELLO-CARD-ID): mensagem
```

Aqui, o tipo e o TRELLO-CARD-ID devem se referir a branch que está sendo utilizada para o desenvolvimento. Já a mensagem deve descrever brevemente o conteúdo daquela alteração.

A vantagem de manter o tipo e o TRELLO-CARD-ID na mensagem de commit é que após realizado o merge a informação da origem daquela modificação fica explicíta e facilita muito a identificação e investigação de possíveis erros no código.

### Mensagens de commit com descrição longa
Para as mensagens de commit que necessitarem de uma descrição mais detalhada do que foi implementado, recomendamos o seguinte padrão:

```
tipo(TRELLO-CARD-ID): resumo da mensagem

A mensagem detalhada da implementação.
```

## Incremento de versão semântico

Para melhorar a previsibilidade das releases, recomenda-se a utilização do versionamento semântico (semver) que resumidamente, divide as releases em três tipos MAJOR, MINOR E PATCH. Cada release deve ser categorizada em um dos três tipos da seguinte maneira:

### MAJOR

Deve-se fazer um release MAJOR (1.0.0 -> 2.0.0) quando são liberadas funcionalidades novas que necessitem adicionar módulos nativos na aplicação, ou funcionalidades que mudem drasticamente o funcionamento/estrutura/layout do aplicativo.

### MINOR

Deve-se fazer um release MINOR (1.0.0 -> 1.1.0) quando são liberadas funcionalidades incrementais a uma versão, sem a necessidade de novos módulos nativos e também sem grandes alterações estruturais no aplicativo.

### PATCH

Deve-se fazer um release PATCH (1.0.0 -> 1.0.1) quando são liberadas correções para a aplicação em produção, nesse caso não podem ser adicionados/removidos módulos nativos e dependendo do caso podem ser utilizadas ferramentas como o Microsoft App Center (aka Code Push) para evitar o tempo de aprovação e revisão das lojas de aplicativos.

## Trabalhando com branches

Dado que uma branch <nome_da_branch> está atrás da `master`, você pode seguir o seguinte processo, para atualizar ele com a master:

 1. Verifique se todas as mudanças feitas estão commitadas e que nada ficou no em `stash`;
 2. Faça um push para a branch remota: `git push origin <sua-branch>`
 3. Retorne a branch master: `git checkout master`
 4. Atualize a master: `git pull origin master`
 5. Volte para a sua branch: `git checkout <sua-branch>`
 6. Faça rebase da master: `git rebase master`
 7. Se conflitos aparecerem, resolva eles e então adicione as resoluções (`git add <arquivo-arrumado>`), e após resolver todos os conflitos continue o rebase (`git rebase --continue`)
 8. Após o rebase você agora precisa atualizar a sua branch remota: `git push -f` (sim `-f`, porquê após o rebase os seus commits tiveram seus hashes atualizados)
 9. Agora você pode finalmente criar o Pull Request (PR) e pegar um pouco de café.


 ## Referências

 * [Still using GitFlow? What about a simpler alternative?](https://hackernoon.com/still-using-gitflow-what-about-a-simpler-alternative-74aa9a46b9a3)
 * [Karma Commit Messages](http://karma-runner.github.io/1.0/dev/git-commit-msg.html)
 * [Semantic Versioning](https://semver.org/)
