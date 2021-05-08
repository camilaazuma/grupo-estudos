pauta grupo de estudos dia 12/08/2020


participantes: Renato, Giu, Karina, Victor, Larissa, Camila, Gislene, Pedro

O que foi dito:

- Sobre Interapobilidade:
  * Definição: O quanto vc consegue garantir q 2 sistemas se conversem, e entendam o dialogo entre eles.

* Sobre modicabilidade:
  * “O quanto que a gente consiga prever que o sistema consiga sofrer mudanças”
  * Associação com agil, para evitar mudanças de base constantes
  * Vários aspectos que tem que pensar sobre o sistema; Previsão de mudancás… tecnologia… para que as mudanças no fim não sejam mais caras do que a preparação das mudancasno futuro
  * Não dá pra planejar mudar tudo;
  * Tentar se preparar para as coisas que mais mudarão no sistema futuramente
  * Principais medidas: Tempo e dinheiro investido com Vs sem preparação da mudança
    * Considerar também custo de Oportunidade.
  * Considerar:
    * Interferencia de qualidade;
    * Inserção de defeitos;
    * Bugs
    * inconsistencias
  * Táticas adotáveis para aumentar modicabilidade do sistema:
    * Acoplamento; Overlap de responsabilidade de um módulo
      * Tentar imaginar o que acontece qdo se altera um módulo, em relação aos demais módulos;
    * Coesão; Os módulos devem ter responsábilidades únicas
      * Tentar predizer mudanças em um único módulo
      * Se um módulo alterado afeta no comportamento de outros módulos, este possui mais responsabilidades que podem afetar coesão do sistema.
      * Coesão serve para identificar responsabilidades dos módulos
    * Divisão do módulo, para diminuir tamanho do mesmo.
    * Encapsulamento da responsabilidade;
      * Quando cria uma interface, você evita que 2 módulos possuam a mesma responsabilidade.
      * Também evita puxar mais responsabilidades do que deveriam
    * Intermediabilidade;
    * Restringir dependencias;
      * Private/ Protected
      * Não fica explicito como o módulo funciona.
    * Elementos arquiteturais duplicados podem ser Refatorados.
      * Quando acontece, tentar criar um módulo único, mesmo que precise ser parametrizado.
    * Parametrização diminui a dificuldade de mudanças no projeto, principalmente por que os módulos que usam parâmetros possuem menos interdependencias internas. Parametros são explicitos para os desenvolvedores.
      * Ex.: Resource files.
      * Plugins
    * Aspectos.
    * Coordenation module: Gerar coordenação entre módulos distintos. Coordenação entre módulos acaba gerando dependencia.
    * O model em sí gera dependencia do sistema como um todo.
    * Buscar fazer crescimento horizontal do sistema, ao inves de ser vertical (para diminuir dependencia de módulos; diluir o máximo possível)
    * A escolha da tecnologia pode interferir na dificuldade de mudanças em específico do sistema.
* Sobre Performance:
  * Cap. explica como performance smp foi o motivador em pensar em arquitetura de sistema.
  * Conforme custo de hardware Vs desenvolviment começou a inverter, performance começou a sofrer concorrencia com outras qualidades
  * Todos os sistemas possuem requisitos de performance implicitos/esperados.
  * Performance é muito associado a escalabilidade
  * Fonte: Usuário; estímulo: Evento iniciado; Cenário encerra quando existe um feedback. Eventos podem ser periódicos ou distribuição estatística; ou arbitrário.
  * Objetivo de performance: Gerar uma resposta no evento dentro de uma métrica baseada em tempo, para ser resolvido quando entra no sistema.
  * Pode estar sendo processado na requisição; Ou está bloqueado
  * 2 categorias de tática para gerenciar recursos e melhorar performance:
  * Para controlar demanda de recursos:
    * Redução de frequencia de sinais captados em uma stream de dados;
      * Pode baixar a fidelidade da stream, mas manter a consistencia do vídeo
      * Ex,: Diminuir a qualidade de vídeo e/ou da música, mas manter a consistencia
      * Custo: Baixa fidelidade da informação, mas garantindo consistencia da informação
    * Limitar a resposta de eventos
      * Colocar os eventos em uma fila, e vai atendendo eles de um em um.
      * Garantir que a fila seja grande o suficiente para todo mundo; Ou ir garantindo a eliminação dos eventos, caso a fila esteja cheia.
      * Políticas de eventos ignorados. Vs ser aceitavel perder eventos
    * Priorizar eventos;
      * Atender o que é crítico primeiro;
      * Atender muitos eventos críticos constantemente acaba aglomerando eventos com baixa prioridade. Como tratar isso
    * Diminuir overhead;
      * Economizar no tempo para se comunicar com estes módulos
      * Colocar tudo no mesmo lugar
      * Custo modificabilidade Vs performance.
    * Limitar tempo de execução
      * Definir qto tempo um evento pode ser executado;
      * “Alimentar os gêmeos; um de cada vez”
    * Aumentar eficiência dos recursos
      * Refatorar o código em áreas críticas para diminuir a latencia de execução
      * Modificabilidade Vs Performance.
  * Gerenciamento de recursos
    * Ao invés de se preocupar com a demanda que está chegando, melhorar o sistema para suprir as demandas que estão chegando
    * Aumentar os recursos
      * Ex.: Aumentar processamento; Memória; Escalabilidade das máquinas
    * Introduzir concorrencia
      * Pode acabar gerando race conditions; Ou seja, inserção de bugs
    * Manter réplicas de serviço
      * Distribuição de tarefas entre serviços.
      * Load balancer.
    * Replicas de dados
      * Cache;
      * Ter várias cópias de bancos
    * Restringir o tamanho da fila
      * Quem chega no final, ele pode acabar sendo não atendido.
      * Qdo não puder atender um evento, o que acontece com ele? Devolve um erro… não pode perder eventos… (?)
    * Agendar recursos
      * Políticas de scheduling
      * Filas
      * Prioridades fíxas Vs dinâmica
  * Performance pode ser importante, mas pode deixar coisas de lado como custo.
  * É aceitável?
* Sugestões:
  * Publicar o conteúdo intelectual gerado nas reuniões em um blog colaborativo e aberto.
    * Exs.: Hugo; Medium; etc.


