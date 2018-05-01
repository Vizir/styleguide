## Criando APIs

Um bom início é o guia criado pelo Heroku: [https://geemus.gitbooks.io/http-api-design/content/en/](https://geemus.gitbooks.io/http-api-design/content/en/)

Use o guia acima como uma referência e para criar um `check-list`, do que a sua API precisa ter, por exemplo adicionar [request-id](https://geemus.gitbooks.io/http-api-design/content/en/foundations/provide-request-ids-for-introspection.html) é algo barato, e que geralmente não lembramos de fazer ao criar APIs.

### Documentando APIs

Uma boa abordagem para criação de APIs, é primeiro documentar ela, principalmente, quando a API vai ser usada por vários times/apps. Pois a sua documentação é uma forma de se aprofundar no contexto, e assim entender-lo melhor antes de começar a codificar.

Ferramentas que costumamos usar na Vizir são:

* [apiary](https://apiary.io/)
* [Swagger](https://swagger.io/)

### Testando  APIs

O próprio [apiary](https://apiary.io/) e [Swagger](https://swagger.io/) fornecem formas de testar, porém muitas vezes eles não existem, seja porquê não criamos ou estamos consumindo uma api de terceiro. Para estes casos o sensacional  [Postman](https://www.getpostman.com/) é a solução. Sendo uma boa prática criar collections, usando variáveis de ambiente, e compartilhado-as na Intranet/Slack com o time.
