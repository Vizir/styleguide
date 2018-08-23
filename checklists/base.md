## Checklist básico

A ideia do checklist abaixo, é auxiliar diferentes momentos do desenvolvimento, e principalmente o início do desenvolvimento, onde algumas escolhas são menos custosas.


### Nunca fazer

* Não adicionar chaves (da AWS, banco, etc) no projeto, usar sempre variável de ambiente

### Fluxo de trabalho e git

* Definir um padrão para o fluxo do git em todos os projetos.(pelo menos os novos)
* Antes de fazer o PR/commit, analisar o código gerado com `git diff` e olhar por possíveis erros e melhorias que podem ser feitas
* Gerar commits pequenos que facilitam o entendimento do que foi feito
  * `git add --patch`
* Dividir os commits em escopo de responsabilidades. Às vezes rola de fazer um único commit e colocar na mensagem que fez X e Y. Nesse caso, melhor fazer dois commits separados, um para X e outro para Y. Se precisar reverter, fazer cherry pick de somente uma parte, facilita bastante
* Enviar para o master sempre com `no-ff`

### Práticas de codificação

* Usar injeção de dependência
* Separar código de infraestrutura, do código de domain
* Não criar código procedural, evitando funções longas, ifs complexos, muito alinhamento (https://williamdurand.fr/2013/06/03/object-calisthenics/)
* Não criar mais de 3 níveis de alinhamento
* Separar as funcionalidades, primeiro em funções, depois em arquivos, camadas, módulos, etc (http://blog.caelum.com.br/principios-do-codigo-solido-na-orientacao-a-objetos/)
* Encapsular códigos de terceiro para você poder ter controle sobre o uso dele e facilitar caso seja necessário trocar
* Funções de controles devem ser pequenas e tratar apenas o retorno HTTP para o client

### Ambiente de desenvolvimento e documentação

* Rodar o projeto no docker
* Criar um README e testar o README, principalmente o setup do projeto
* Criar um CONTRIBUTING (https://pastebin.com/ndFpBTFr)
* Se não estiver usando algum framework, ou estiver estendo alguns conceitos do framework, documentar qual a abordagem/conceitos estão sendo usados (ex: https://bitbucket.org/myvizir/bemvc-app/src/master/)
* Configure o lint (https://bitbucket.org/myvizir/eslint-config-vizir/src/master/) e use o https://github.com/typicode/husky pra configurar rodar ele antes de cada push, e também rodar os testes
* Definir se o projeto será documentado (README, Wiki, comentários, commits, etc) em pt-br ou en (en para código sempre)
* Configurar o CI e CD do projeto (usar o BitBucket Pipelines)
