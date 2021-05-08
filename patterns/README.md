## Geral

[Artigo no DZone](https://dzone.com/articles/software-architecture-the-5-patterns-you-need-to-k#:~:text=Layered%20Pattern,service%20to%20a%20higher%20layer) [tem uns patterns e umas explicaçõezinhas] (2018)

[Aula de Padrões Arquiteturais](https://edisciplinas.usp.br/pluginfile.php/4641854/mod_resource/content/1/Aula%209%20-%20Padr%C3%B5es%20Arquiteturais.pdf)

  * Aula das profas. Elisa Yumi Nakagawa e Lina Garcés do ICMC - USP
  * O começo da aula é meio esquisito, mas a lista de patterns é bem completa e o conteúdo é aprofundado na medida certa, com exemplos visuais do funcionamento de cada pattern.

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

## P2P (Peer to Peer)

* [Os nós possuem as mesmas responsabilidades e capacidades](https://www.techopedia.com/definition/454/peer-to-peer-architecture-p2p-architecture#:~:text=Peer-to-peer%20architecture%20(P2P%20architecture)%20is%20a,are%20dedicated%20to%20serving)

* Existem tanto arquiteturas hibridas quanto puras usando P2P

* Vantagens:
  * descentralização de redes e estruturas;
  * O que também significa de que o serviço fica menos dependente de um servidor central para prover servicos aos seus clientes, visto que todos possuem as mesmas responsabilidades.
  * Diminui consumo de banda dos servidores, visto que os clientes também possuem responsabilidades entre eles nos nós

* Desvantagens:
  * Segurança: Os nós estão sujeitos tanto as vulnerabilidades de clientes remotos, quanto de servidores. 
    * Se segurança é um requisito forte do sistema, P2P pode ser uma decisão mais complexa de se empregar
  * Implementação exige que todos os nós saibam mapear a rede (com tabelas de roteamento)
  * Ele acarreta em [decisões sociais mais difíceis de controlar e mensurar](https://en.wikipedia.org/wiki/Peer-to-peer#Social_implications):
    * Controlar pirataria é difícil, por conta de que P2P estimula anonimicidade dos nós como um todo.

* [Alguns exemplos](https://en.wikipedia.org/wiki/Peer-to-peer#Applications):
  * Transferencia de arquivos (Ex.: UTorrent)
  * Redes de browsers para comunicação de paginas html (Ex.: TOR)
  * Multimidia (para transferencia de música e vídeos) (Ex.: Spotify tem uma solução híbrida utilizando P2P)
  * Sistemas de atualização de software (Ex. Client de jogos; Sistema de update do Windows 10)
  * Sistemas de CriptoMoedas; (Carteira e assinatura de bitcoins é facilitada por conta da arquitetura p2p)
 
 
