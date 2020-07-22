## Geral

[Artigo no DZone](https://dzone.com/articles/software-architecture-the-5-patterns-you-need-to-k#:~:text=Layered%20Pattern,service%20to%20a%20higher%20layer) [tem uns patterns e umas explicaçõezinhas] (2018)

[Software Architecture Patterns](../material-base/software-architecture-patterns.pdf), Mark Richards [livro] (2015)

`Blog: parte 1 parte 2 [tá mais pra uma lista de alguns patterns] (2019)` PRECISA CORRIGIR

[Livro Software Architecture in Practice](../material-base/software-architecture-in-practice-3rd.pdf) - cap. 13 Architectural Tactics and Patterns

## Blackboard

Artigo "[Two complementary patterns to build multi-expert systems](./lalanda.pdf)" - Philippe Lalanda

  * Explica bem o conceito no começo do artigo, depois propõe uma adaptação interessante

Artigo na Medium "[Why use the blackboard pattern](https://medium.com/coinmonks/blackboard-pattern-ed3981551908)"

  * apresenta um exemplo prático, acompanhado do código no Github do rapaz
  * https://github.com/streklin/home_services_experimental/blob/master/rover_platform/src/Services/Blackboard.cpp

## Broker

Artigo que explica como é usado o Broker (nesse caso é o RabbitMQ) no Runtastic App
  * https://www.runtastic.com/blog/en/rabbitmq-message-bus/

## Pipe/Filter

Artigo no Medium (com exemplos no final)
  * https://medium.com/@syedhasan010/pipe-and-filter-architecture-bd7babdb908

## Interpreter

Artigo no Medium com exemplos
  * https://medium.com/@sawomirkowalski/design-patterns-interpreter-5b4c0e2b832f

## Event Driven

  * microsserviços assíncronos
  * topologia:
    * mediator
    * broker
  * escala fácil: feito de vários módulos que processam/recebem os eventos (single purpose)
  * mediator: evento entra na fila, chega num módulo mediador que redireciona o evento para cada step
  * broker: os eventos já são direcionados para os módulos do processo. Ex: ficha de hospital (cada processor processa e emite um evento dizendo que acabou. Thank you, next!)
  * muito usado para IoT
  * difícil de testar a integração

  https://dzone.com/articles/demystifying-the-event-driven-architecture-making
  
  https://www.redhat.com/en/topics/integration/what-is-event-driven-architecture
  
  https://www.oreilly.com/library/view/software-architecture-patterns/9781491971437/ch02.html
