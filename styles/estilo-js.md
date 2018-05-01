# JavaScript

Usamos o guia de estilo do [Airbnb](https://github.com/airbnb/javascript).

A sua escolha foi devido ele ter se tornado o mais usado lint, tanto em clientes nossos, como em vários projetos, ele se mostrou ter as regras mais "balanceadas".

## Instalação

Primeiro instale estlint, junto com o lint do airbnb:

`yarn add eslint eslint-config-airbnb --dev`

Agora crie um arquivo chamado `.eslintrc`, com o seguinte conteúdo JSON:


```json
{
  "extends": "airbnb"
}
```

Pronto o seu projeto agora já estará estendendo o lint do Airbnb e você poderá sobrescrever as regras, de acordo com as necessidades do projeto e equipe.
