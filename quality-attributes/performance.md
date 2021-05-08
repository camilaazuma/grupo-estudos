# Performance

performance has been the driving factor in system architecture durante a história

- conforme a taxa custo/performance de hardware continua a cair e o custo do desenvolv de software continua a subir, outras qualidates apareceram para concorrer com performance

todos os sistemas tem requisitos de performance, mesmo que não sejam explícitos

performance é frequentemente associado a escalabilidade

começa com um evento chegando no sistema
eles podem chegar de forma:

- periódica (10 em 10 ms)
- estocástica (de acordo com alguma distribuição estatística)
- esporádico (não seguem nenhum padrão)

## Táticas

o objetivo das táticas de performance é gerar uma resposta a um evento dentro de um determinado tempo

depois que um evento chega, o sistema pode ter 2 estados: 

- processando (trabalhando na requisição)
- Bloqueado (incapaz de responder por estar):
    - aguardando recurso (quando um recurso pode ser usado por um client por vez
    - disponibilidade: algum recurso pode estar indisponível ou offline
    - dependencia de outros serviços (precisa esperar resposta de outro serviço)

2 categorias de táticas: controlar a demanda de recursos ou gerenciar recursos

- controlar a demanda de recursos
    - manage sampling rate: reduz frequencia de sinais capturados de um stream de dados. baixa fidelidade mas stream consistente > perder pacotes de dados
    - limitar a resposta a eventos: bota numa fila e espera sua vez
    - priorizar eventos: se nem todos os eventos são igualmente importantes, prioriza os mais críticos e até ignora os baixa prioridade
    - reduzir overhead: hospedar componentes cooperativos em um mesmo lugar pra evitar o delay da comunicação entre eles. (modifiability/performance tradeoff)
    - limitar o tempo de execução:  definir o tempo que um evento pode levar pra ser processado
    - aumentar a eficiência dos recursos: melhorar os algoritmos em áreas críticas pra reduzir a latencia
- gerenciar recursos
    - aumentar recursos: processador mais rápido, processadores extras, memória extra, mais rede.
    - introduzir concorrência: fazer coisas em paralelo. (tomar cuidado com race conditions.)
        - concorrencia (importante, mas precisa de cuidado)
        mútiplas threads de execução independentes
        quando 2 ou mais threads executam o mesmo statement rola uma race condition (estado compartilhado)
        é um bug difícil de descobrir pq é esporádico e depende do timing
        resolve com um lock no state
    - manter replicas do serviço: distribui as tasks entre as cópias (load balancer faz a distribuição)
    - manter replicas de dados: Cache. Inclui a responsabilidade de manter a sincronia e consistencia entre os dados
    - restringir o tamanho da fila: controla a qtd máxima de eventos que chegam querendo biscoito. Precisa de uma política pra quando um evento não puder ser atendido ou se ignorar eles é aceitável
    - agendar recursos: adotar políticas de scheduling (FIFO, fixed priority, dynamic priority, Earliest-deadline-first, Least-slack-first)
        - slack time é a diferença entre o tempo de execução restante e o deadline