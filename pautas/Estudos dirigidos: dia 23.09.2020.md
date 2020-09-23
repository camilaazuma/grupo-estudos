Grupo de estudos do dia 23.09.2020

Integrantes: Giuliana,Tiago (Tig), Victor (Vitu), Pedro, Larissa, Gislene, Camila, Karina

O que foi discutido:



*   Talk da Camila sobre arquitetura monolitica
    *   Talk de engenharia em RD - acontece quinzenalmente.
        *   Ex.: Estratégia para evitar estouro de emails em periodos como blackfriday / periodos de pandemia
        *   Vivem fazendo mudanças para comportar os usuários .
    *   Monolitos não deveriam ser a primeira opção;
        *   Pense na arquitetura antes de começar o desenvolvimento.
        *   Tomar MTO cuidado ao transformar um sistema monolítico para se tornar micro serviço.
            *   Separação dos módulos não fica distinto.
            *   "Muitas bagunças espalhadas"
                *   Os blocos de lama.
        *   Primeiro: Modularizar o monolito;
        *   Depois começar a quebrar
        *   Como estão empregando domain driven design.
            *   Utilizando teorema do conjunto para determinar o domínio dos módulos.
            *   Tudo o que tem a ver com o dóminio de um respectivo tópico, deve ser englobado em um mesmo bloco/ modulo.
                *   Decisão arquitetural
            *   Aplicar isso nos seus respectivos componentes.
            *   Garantir que dominios não se misturem constantemente.
        *   Depois, aplicar contratos de API (interfaces) para acessar diferentes domínios.
            *   Se não usar dessa forma, acaba invadindo o domínio alheio.
            *   Se não houver essa distinção, acaba voltando para o monolito.
        *   Eles utilizam a camada de rede como interface para garantir que não aconteça unir domínios por acidente ou preguiça.
    *   Camila irá compartilhar um livro sobre referência de domain driven.
*   Essa discussão seria interessante com o renato, visto que ele curte esse tópico.
*   **Conversaremos com Renato para ver se ele consegue organizar um talk para falar de Domain Driven Development.**
*   RD tem um monte de micro serviços - micro componentes.
*   Componentes do front end também podem sofrer essas mudanças de arquitetura?
*   Arquitetura de micro serviços pode acarretar em muitas ferramentas para monitoramento dos serviços.
*   Giu mostrou uma aplicação do CRM de RD para mostrar a distinção de rodar microserviços com componentes visuais para criar micro front end.
*   Discussão sobre os próximos tópicos:
    *   Temas remanescentes:
        *   Tiers/ Layered Patterns - Caso queiramos dar + ênfase em padrões de camadas. Importante na nossa área, pode ser importante.
            *   Já possui material levantado para didática.
        *   Databases: Relacionais e não-relacionais
        *   Arquitetura monolíticas - Case do linkedin.
        *   Picking the right technology - Não sabemos se há material para isso
        *   Cases;
        *   Sessão de talk com Javier/ Thiagão;
            *   Exporem a linha de pensamento deles na hora de arquitetar o sistema.
            *   Vai precisar de disponibilidade deles + tempo deles para isso
            *   Tentar fazer isso dentro do próximo mes.
        *   Design Patterns - Não relacionado com arquitetura de software.
            *   Focado + em qualidade de software doq de fato arquitetura de software.
    *   Cases serão nosso breakpoint para verificar se o tamanho dos temas remanescentes está curta ou não
    *   Talks do Thiagão/Javier - Se já tiver alguma ideia + específico, já definir quando eles podem ter tempo para nós, e já notificar com até 1 mês de antecedência.
        *   Pedimos para a Gi para que a Inspira pudesse providenciar essas horas para o grupo.
        *   **Lari irá conversar com o Thiagão** para ver a disponibilidade
        *   Camila propõs que quem for apresentar, determina quanto tempo precisa.
        *   Pedro propos um timeline, e impactos dos cases ao longo da carreira deles.
        *   A ideia é ver o racional da aplicação / ver como eles resolvem arquiteturalmente um problema.
        *   Propostas de temas:
            *   Deixar na mão deles para definir um case e resolver.
                *   Se não tiver uma ideia, propomos uma ideia
            *   Utilizar um case no cronograma com um comparativo de como está no futuro;
            *   Propor um case da inspira no qual eles participaram da decisão.
                *   Explicar a linha de raciocínio na hora que eles definiram.
        *   Proposta Final: eles fazerem um walkthrough de algum case que eles participaram da inspira.
*   Com o grupo: Fecharemos para daqui 2 semanas: Tiers/ Layered Pattern

[https://github.com/camilaazuma/grupo-estudos/blob/master/material-base/Patterns%20of%20Enterprise%20Application%20Architecture%20-%20Martin%20Fowler.pdf](https://meet.google.com/linkredirect?authuser=0&dest=https%3A%2F%2Fgithub.com%2Fcamilaazuma%2Fgrupo-estudos%2Fblob%2Fmaster%2Fmaterial-base%2FPatterns%2520of%2520Enterprise%2520Application%2520Architecture%2520-%2520Martin%2520Fowler.pdf)
