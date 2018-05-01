## Marco Zero

O início da nossa aventura começa passando por pontos mais relacionados a *soft skills*, que são mais valorizados, do que as *technical skills* na Vizir.

### O que mais buscamos no nosso processo seletivo

Se você está na Vizir, provavelmente passou pelo nosso processo seletivo (sim, há alguns Vizires que não passaram, por já termos trabalhado antes). Nosso processo não é o mais rígido, mas há dois pontos base que buscamos, ao contratar:

* **Ser uma pessoa legal**: mais subjetivo que isso, impossível. Mas tem haver com as *soft skills* que comentamos, que abrange o trabalho em equipe, postura, gostos, e principalmente se a pessoa compartilha os mesmos valores que temos na Vizir;
* **Saber programar**: na maioria das vagas buscamos muito mais alguém que tenha uma boa fundação, do que um especialista em tecnologia X. Isso deve-se a natureza dos nossos projetos e desafios, onde a especialidade muda com frequência, e ter uma base sólida é muito mais importante, e isso em termos mais objetivos passar por: modelagem de Software, como usar os tipos corretos, abstração, separação de responsabilidade; saber criar testes unitários e que cobrem cenários de negócios.


### Nossos princípios

* Feito é melhor que perfeito
  * desenvolver software é um trabalho criativo, portanto, como todo trabalho criativo se não colocarmos uma restrição de  tempo, pode tomar o tempo "infinito". Diante da restrição do tempo, este princípio precisa ser adotado a cada tarefa, por isso, é importante trabalharmos em sprints de X semana (geralmente 1 ou 2 semanas), estimarmos as tarefas, e a cada execução colocarmos metas "pessoais", pois essas restrições irão nos ajudar a chegar no "feito é melhor que perfeito", e ao fim do nosso trabalho ter ele entregue, rodando em produção.
* Deixe o código melhor do que você encontrou
  * é uma das formas de aplicar o [kaizen](https://en.wikipedia.org/wiki/Kaizen), que significa "melhoria"/"mudar para o melhor" em japonês. E também uma forma de não deixar [janelas quebradas](https://blog.codinghorror.com/the-broken-window-theory/).
* Quando estiver travado, busque ajuda
  * desenvolver é uma tarefa complexa, portanto é comum ficarmos travados em certas tarefas, principalmente quando é a primeira vez que estamos realizando. Por isso, pedir ajudar é a melhor forma de superar esse "travamento", que tem impacto tanto na auto-estima, como no andamento do projeto. Como recomendação, ao ficar mais de 2 horas travado, é bom pedir ajudar seja para o(a) Vizire do lado, ou no Slack da Vizir.
* Compartilhe o seu conhecimento
  * além de ser um ótimo exercício pra solidificar conhecimento, é fundamental pra termos uma equipe produtiva e estarmos sempre aprendendo algo novo.


### Boas práticas

#### Boas práticas de equipe


* Esteja sempre aberto a críticas e sugestões, o código que você cria, é do coletivo;
* Somos no geral péssimos piadistas, porém o bom-humor é uma ótima ferramenta para criar um ambiente saudável e prazeroso de se trabalhar (ahh q delícia cara!);
* Saiba respeitar as diferenças. Na Vizir a diferença sempre foi bem-vinda, e está mais que provado em vários ramos, que a diversidade traz inovação e bons resultados as empresas e pessoas;
* Seja um guardião da saúde e efiência da equipe, seja durante as retrospectivas ou no próprio dia-a-dia. Lembre-se que o entregue é sempre melhor que o perfeito, porém, o entregue de hoje, é bom ser melhor do que o de ontem;
* Aceite falhas, programar é um esforço grande cognitivo e assim, fadado ao erro, então use eles para melhorar, e não para te deixar pra baixo.

#### Boas práticas de codificação

* Ao longo do projeto sempre atualize as libs, pois desta forma você ganha várias novas funcionalidades, e inclusive sempre leia o changelog/releases, e também torna o processo de atualização menos impactante para a velocidade do projeto;
* Ao encerrar o projeto, "congele" as versõe s das libs, para evitar problemas futuros por atualização de versão. Assim, caso alguém queira atualizar alguma dependência no futuro, ela terá que realmente atualizar no package.json e testar a aplicação;
