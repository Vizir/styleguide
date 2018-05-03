## Padrões de código

Aqui você irá encontrar padrões de código, que são independentes da linguagem/stack, e que ao longo do tempo, se provaram bons padrões, nos ajudando a entregar software de qualidade.

### Gerenciamento de dependências

* Ao longo do projeto sempre atualize as libs, pois desta forma você ganha várias novas funcionalidades, e inclusive sempre leia o changelog/releases, e também torna o processo de atualização menos impactante para a velocidade do projeto;
* Ao encerrar o projeto, "congele" as versões das libs, para evitar problemas futuros por atualização de versão. Assim, caso alguém queira atualizar alguma dependência no futuro, ela terá que realmente atualizar no arquivo de dependências (ex: `package.json`/`Gemfile`) e testar a aplicação;
