<!-- Copy and paste the converted output. -->

<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 0.568 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β29
* Thu Sep 17 2020 12:49:43 GMT-0700 (PDT)
* Source doc: Pauta dia 16.09
----->


Grupo de estudos do dia 16.09.2020

Integrantes: Karina, Larissa, Tiago, Victor, Pedro, Giuliana, Camila

O que foi discutido:



*   Quem fez as tarefas nesta quizena: Giu, Karina, Camila
*   Apresentação da Camila:
    *   Estudo: Tik Tok
    *   Fundamentos base do tiktok:
        *   Login; Configuração; interatividade com posts; busca
    *   Ponto chave:
        *   Real time Analytics, para melhorar o sistema de recomendação direcionado aos usuários
        *   Geolocalização
        *   Push Notification (mecanismo de vício do sistema)
    *   Patterns:
        *   Pipe/filter
            *   Faz sentido para aplicar internamente na edição dos vídeos na camera
        *   Event Driven:
            *   Faz sentido na live e interações entre os usuários. Também dá pra criar um fluxo aberto de interações conforme atividade dos usuários
        *   P2P
            *   Faz sentido no ponto de vista dos vídeos (para lives de sertanejo com 500 mil pessoas)
    *   Atributos:
        *   Performance:
            *   por ser um app dinâmico na hora.
            *   Quer tudo ao mesmo tempo
            *   Importante para streaming.
            *   Formas de otimização para não sobrecarregar a banda do usuários, e otimizando a performance e consumo de banda.
        *   Usabilidade
            *   App para prender as pessoas por muito tempo.
            *   Esquema de recomendação direcionada por analytics -> Te manter o máximo de tempo possível
        *   Testabilidade:
            *   Por conta da carga de usuários,
        *   Availability
            *   Por conta do público alvo ser jovens impacientes que
        *   Mensão honrosa - Segurança
    *   Amplamente elogiado por toda a equipe. Kudos pra camila! :party:
*   Apresentação da Giu:
    *   Estudo: Programa do imposto de renda Brasileiro;
    *    Tema bem diferente dos demais
    *   Não necessariamente as pessoas querem usar… mas elas eventualmente precisarão utilizar.
    *   Expectativa Vs Realidade
    *   Quality Attributes:
        *   Availability
            *   Vale tanto para app quanto desktop;
            *   Necessidade média -> servidor do programa precisa estar disponível ao longo do tempo.
                *   Pode ser submetido mais tarde, visto que o programa salva o estado atual do imposto
                *   problema surge quando prazo de entrega fica próximo, e sistema está fora do ar
        *   Interoperability
            *   Interação entre programa/app e o servidor com informações.
            *   Também precisa interação do servidor com outros sistemas, para auditar os usuários.
                *   Mais o sistema fazer a busca dos usuários, do que o contrário
                *   API autenticavel, para não permitir sensibilidade de fornecimento de informação
        *   Modifiability
            *   Lançam um programa novo todo ano no desktop;
            *   App é o mesmo; mas lançam anualmente um update.
                *   Modificações normalmente provavelmente deve ser necessários para ajustes de bugs
            *   Ao mesmo tempo, é um programa que tem a garantia de que há atualizações e ajustes anualmente.
            *   Layout se preservou durante as gerações;
            *   antigamente, tinha 2 programas para registro e submissão dos serviços
            *   Modificabilidade é para garantir que o programa não se torne obsoleto.
        *   Performance:
            *   Relevância baixa?
            *   Tem que se rodar bem em múltiplos devices, até mesmo os mais obsoletos.
        *   Segurança:
            *   Possui dados sensíveis dos usuários: Informações pessoais + informações bancárias e renda dos usuários
            *   Preocupação com
                *   Interceptação dos dados;
                *   Vazamentos das informações do usuário
                *   Medidas básicas de autenticação dos usuários
                *   Evitar risco de informação falsa na submissão
        *   Testabilidade
            *   Faz sentido, para garantir que o app esteja funcional e enviando informações corretas aos usuários
        *   Usabilidade:
            *   Deveria ser simples, visto que atinge todos os públicos
            *   Ao mesmo tempo não há alternativas. Mesmo que não seja intuitiva, os usuários são indiretamente forçados a ter que utilizar este sistema
            *   O app é ok, e parece ser mais facil de usar do que a versão desktop
*   Dificuldade de sistemas não serem unificados. Mas com o começo da digitalização das maiores responsabilidades civis das pessoas (carteira de trabalho; Imposto de renda) permite melhor centralização dos dados da população - Resumo das citações dentro do tema “imposto de renda brasil”
*   Apresentação da Karina:
    *   Arquitetura de software - decisões que você gostaria de ter tomado antes no projeto
    *   Comum para todos os casos: Não esperavam escalar no nível que foi escalado Vs pressão para lançar logo o sistema.
    *   Exemplos de casos que tiveram que ter esforços para dar certo, com redesign
        *   Airbnb: relatórios financeiros
            *   Sistema antes: MySQL ETL pipeline (extrair, transformar e carregar)
            *   Principal qualidade afetada: Escalabilidade, testabilidade, modificabilidade;
                *   Antes: Relatórios eram gerados toda a noite.
                *   Depois: Tiveram que mudar para dia sim, dia não a geração dos relatórios. Testar os fluxos eram muito demorados, e toda vez que queriam incluir features novas, o esforço era dobrado.
            *   Depois: Event Based Financial Report
                *   Criaram o módulo do sistema financeiro
                *   Dependendo do comportamento do sistema, o modelo atua ou não
                *   Cada módulo só precisa gerar os eventos requisitados do sistema financeiro
                *   Também tiveram que desacoplar o sistema financeiro da lógica do produto, para conseguir aplicar esta refatoração.
        *   Dynein: Job queuing system:
            *   Usam este sistema para tarefas críticas
                *   in-app messaging;
                *   tarifa dinâmica
            *   Principais problemas: escalabilidade (pois os jobs eram executados dentro de um cluster da própria aplicação, monolítica); Reliability; Modificabilidade;
        *   Principal dificuldade: conseguir prever o quanto o projeto cresce Vs pressa para entregar o produto.
        *   Dropbox:
            *   Problema maior foi escalabilidade de novo
            *   Saber lidar com concorrências (problema da lista ligada cíclica com dois usuários tentando fazer alterações nas estruturas de pastas concomitantemente)
                *   Concorrência fazia dar muito xabu em qualquer alteraçãozinha
*   **Camila falou que vai fazer talk sobre mini monólitos semana que vem**
*   Na semana que vem discutimos qual será o próximo assunto