Grupo de estudos do dia 19.08.2020

Integrantes: Giuliana,Renato, Victor, Pedro, Larissa, Gislene, Camila, Karina

O que foi discutido:



*   Discussão sobre quality attributes Relacionados aos patters dentro das listas dos projetos;
*   **Lição de casa**: Cada um escolher um projeto e tentar discutir sobre isso;
    *   Tirar a abstração do que são os quality attributes, e os patters descritos anteriormente.
    *   Essa discussão parece fazer sentido, promovida por um dos integrantes
    *   Projetos devem ter portes diferentes de escala (gigantes, como Facebook/Youtube Vs outros projetos pequenos)
    *   Estudo deve ser feito com ferramental/framework, ou em lógica de negócio?
        *   “Não conhecer 100% do case”
    *   Prazo: 2 semanas (02/09/2020)
    *   Entre o período de 2 semanas, pessoal já divulgar qual projeto planeja fazer a análise.
*   Apresentação: Testabilidade.
    *   Começo do cap. -> Discussão de que pelo menos de 30% a 50% do custo do sistema é ocupado pela parte de testar o sistema.
    *   Se o arquiteto de software diminuir este custo = ganho grande no processo.
    *   Definição: Facilidade com que o software consegue mostrar os erros e falhas através dos testes. É a probabilidade do sistema ilustrar um erro na próxima iteratividade de testagem da aplicação
        *   Seja este teste manual, ou automatizado.
        *   Detectar erros rapidamente.
    *   Definição:
        *   Programa tem input e output;
        *   Programa possui um estado interno (não necessáriamente o output)
        *   Oracle: Agente que pode ser um teste ou usuário, para determinar se o output está correto com o input, de acordo com a especificação.
            *   O Oráculo diz se está certo, tanto no resultado final, quanto nos quality attributes previamente listados (performance; Tempo de execução)
                *   Baseado em parâmetros previamente determinados.
    *   Fonte: quem está realizando o teste
        *   Pessoa manualmente
        *   Teste unitário/ integração
    *   Estimulo: o que desencadeia o teste
        *   Terminar uma implementação
    *   Artefato: Código produzido
    *   Ambiente: Ambiente do desenvolvimento
    *   Response: Output computado
    *   Response Measure:
        *   Quão efetivo os testes são em determinar erros;
        *   Quanto tempo demora para ter uma cobertura desejada dos testes
            *   Facilidade de trazer cobertura de testes ao sistema;
            *   Quanto tempo leva para executar os testes;
            *   probabilidade de revelar erros na próxima execução dos testes.
            *   Tempo que leva para preparar os ambientes de testes
                *   Configuração
                *   Outros fatores
    *   Táticas de testabilidade:2 frentes principais:
        *   Adicionar controlabilidade e obersabilidade do sistema;
            *   Controlar inputs;
            *   Analizar/ observar os outputs
            *   Tatica: Incrementar este aspecto.
            *   Exemplos:
                *   Determinar estados do sistema
                *   Acessar estado interno do componente através dos módulos
                *   Interfaces especializadas
                *   Métodos de reset; Determinar valores específicos do sistema
                *   Verbose output/ inserção de logs em modelos internos
            *   Abstrair o data source:
                *   Tornar facil substituir o data source
                *   Ex.: Substituição de um banco MySQL Com um arquivo de texto correspondente, por exemplo;
                *   SandBox: Instancia do sistema ser isolada do mundo real;
                    *   Ex.: Zoar o banco totalmente
                    *   Mudanças do sandbox não trazem consequencias ao mundo real/ em produção
                    *   Stubs;  mocks; inserção de dependencia;
                    *   Emular um tempo do dia;
                    *   Virtualizar parâmetros do sistema (bateria remanescente; horário do dia; )
            *   Executable assertions:
                *   Execuções que são feitas antes e depois do teste, para monitorar mudança de valores durante execução do sistema/ teste.
        *   LImitar complexidade do sistema:
            *   Se seu sistema é complexo, é mais dificil testar ele.
            *   Como limitar a complexidade estrutural do seu sistema?
                *   Ex.: Dependências cíclicas.
                *   Ex.: Isolar/ encapsular dependencias de um ambiente externo (boas práticas de código de isolamento de lasses; Responsabilidades únicas)
                *   Reduzir dependencias dos componentes no geral
                *   Software Orientado a Objeto -> Diminuir a complexidade da árvore de heranças
                    *   Não ter uma arvore genealógica grande, cheia de fillhos
                    *   Limitar polymorfismo/ chamadas dinâmicas de métodos
            *   Sistemas em camadas facilitam na limitação de complexidade do sistema
            *   Limitar o não - determinismo do sistema;
                *   Ex.: Multi thread acaba gerando complexidade na testabilidade, por não ser deterministico a ordem de execução de cada thread.
        *   Partes mais críticas do sistema devem ser testadas com mais afinco
            *   Comunicação e coordenação dos seus testes;
            *   Definir abstração de testes que devem ser testadas
            *   Testes devem ser os mais similar ao sistema real, para manter o ambiente de testes o mais próximo do ambente real;
            *   Determinar quais tecnologias estão disponíveis para testar fluxos do teste;
                *   Ex.: Ferramentas de testes para multithreads.
    *   Discussão sobre os dados de teste:
        *   Precisa de um dataset grande e útil para os testes.
        *   Quando existe grande quantidade de registros para performance/ integração.
            *   Escrever um sistema que gere os dados de teste
                *   Garante que cobre todos os cenários extremos, por determinarmos os programas
                *   Custoso; Gerar um programa para testar seu programa.
            *   Ex. 2: Usar banco de produção, mas gerar anonimicidade dos dados reais
                *   Ex.: Eliminar dados sensíveis / mockar dados sensíveis dos bancos reais, nos bancos de testes.
                *   Custoso, quanto atinge uma exceção para detectar um bug.
    *   Netflix: OS testes de macaco;
        *   Cada teste tem um nome de macaco;
        *   Ex.: O macaco do caos destroi processos arbitrários, e o teste monitora como o sistema se recupera desse problema
        *   Ex.: O macaco da latencia insere delays artificiais entre ambiente de cliente e servidor
        *   Ex.: Conformity monkey Fiscaliza as instancias que não utilizam as melhores práticas, e desabilita ela se não seguirem atributos justos
        *   Doctor monkey: Monitora a saúde da instancia
        *   Janitor Monkey: Verifica e remove o lixo dos processos
        *   Security Monkey: Procura falhas de segurança/ vulnerabilidade, e finaliza o processo para garantir que não terá danos piores do que sofrer de fato a vulnerabilidade;
        *   10-18 monkey: Detectar problemas de internacionalização do sistema, e se precisar, desligar a instancia/ alertar sobre o problema.
*   O que faltou neste livro:
    *   Cita as métricas; Mas não explica como medir elas adequadamente.
        *   Ex.: Sobre os testes -> como determinar a priorização do que deve ser testado primeiro?
        *   Faltam exemplos práticos sobre a discussão do livro
    *   Te descrever como introduzir isso no dia a dia;
        *   Ex.: Como desenvolver no dia a dia, para gerar testes e código útil simultaneamente ao sistema?
        *   Desenvolvimento é diferente de descrever o quality attribute; Talvez este exemplo escape do escopo do livro.
        *   Talvez esta crítica deva virar um novo escopo de estudos. Mas não era prioridade do livro analizar isso.
    *   O livro focou fortemente no template de descrever quality attributes;
*   Apresentação: Usabilidade
    *   Definição: tudo aquilo que está relacionado com o quão facil e intuitivo para o usuário utilizar o sistema, tal qual suporte que o sistema fornece ao usuário
    *   Runtime ou configuration time; (quando o usuário utiliza o sistema)
    *   métricas:
        *   Tempo de duração de uma tarefa do usuário;
        *   Numero de erros que o usuário comete no sistema
        *   Resumo: Satisfação do usuário na utilização do sistema!
    *   Iniciativas do usuário e do sistema:
        *   sistema tem que ter bem definido o modelo de operações do usuário
        *   Ação pode vir do usuário, ou do modelo do usuário.
    *   Relação com quality de modificabilidade: A ideia de usabilidade é que o protótipo seja gerado o mais rápido possível para o usuário poder avaliar o sistema
    *   Interface do usuário pode mudar constantemente; ela tem que ter alta modificabilidade para atender as necessidades do usuário.
    *   Pesquisas sobre blogs de tecnologia:
        *   Cai bastante em user experience;
        *   Blog Atlasian: UX ScoreCard for Apps.
            *   Descreve 3 pontos chaves para definir UX
                *   Usability
                    *   Ponto chave: Determinar as tarefas principais do usuário, que ele irá realizar no seu sistema.
                *   Desirability;
                *   Terceiro ponto.
            *   Como identificar tarefas principais:
                *   Brainstorm com empresa (stackholder, funcionários, usuários do sistema, desenvolvedor, marketing… TODO MUNDO);
                *   Ex.: Cisco Juntou 600 tasks do seu sistema, e ordenaram quais dessas tasks são mais utilizadas.
            *   Outras fontes de dados para pegar estas tarefas:
                *   Feedbacks de usuários finais/ reviews que foram feitas em suas aplicações;
                *   Analizar concorrencia com outros serviços parecidos com os seus;
                *   Redes sociais;
                *   Análises de busca;
            *   O sistema deve focar nas tarefas principais dele; Ser destaque nisso, para garantir satisfação dos usuários nas principais tarefas do sistema.
            *   As vezes, é melhor o sistema ser muito bom em fazer as tarefas mais frequentes do sistema, para manter fidelização do mesmo.
        *   Artigo do slack:
            *   Como melhorar a usabilidade do aplicativo, baseado no alcance do dedão em seu aplicativo.
            *   Possui um mapa de onde o dedão alcança naturalmente o sistema;
            *   Utilizar este mapa de limitação física, para aumentar o conforto do desenvolvimento do sistema.
                *   Também colocar as ações mais comuns do sistema nas áreas mais confortáveis da mão.