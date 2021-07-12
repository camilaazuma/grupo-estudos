# Receitas de comidas e drinks dados os ingredientes que tem na cozinha

## Casos de uso

**Escopo**

mVP0

* Usuário pesquisa por receita
    * filtrando pelo nome da receita
    * filtrando pelos ingredientes na receita, incluindo a quantidade máxima dos itens
* Usuário comenta na receita
* Usuário cadastra receita dentro do sistema usando texto manual
* Usuário pede para converter unidades científicas para xícaras/colheres (hardcoded)
* Sistema encontra ingredientes substitutos para as receitas (e fala para o usuário com a voz da bela gil) (hardcoded)
* Usuário edita receita própria

mVP2
* Usuário propõe edição de receita de outro usuário (PR)
    * Receita é versionada
* Usuário cria um fork da receita
* Sistema sugere receitas personalizadas de acordo com o histórico de ingredientes do usuário
* Sistema sugere compras de mercado a partir de ingredientes que liberariam receitas próximas das que o usuário costuma fazer
* Sistema exibe calorias de cada ingrediente na receita

mVPN (recursos mobile)
* Usuário preenche a lista de ingredientes que tem em casa com speech to text (integração com a Alexa)
* Usuário cadastra receita dentro do sistema usando speech to text
* Usuário pede para converter unidades (smart)
* Sistema atualiza a lista de ingredientes que tem na casa do usuário quando ele faz uma compra em site de mercado

MVP
* Usuário cadastra receita dentro do sistema usando foto do livro da vó do Ricardo, com IA pra reconhecer a receita
* Internacionacionalização


**Fora do escopo (mVP0)**

* Usuário se cadastra no sistema
* Usuário faz login no sistema
* Usuário configura visibilidade da receita
* Usuário favorita receitas

## Atributos de qualidade

1. Availability

* tríade consistência e performance
    * consistência não é muito importante
    * podemos pensar ter receitas offline

2. Interoperability

* quais plataformas?
    * site do mercado
    * possivelmente apps de delivery

3. Modifiability

* preocupação é alta, visto como o escopo do projeto expande em suas iterações
* arquitetura evolutiva
* modularização, isolar responsabilidade


4. [Performance](https://github.com/camilaazuma/grupo-estudos/blob/master/quality-attributes/performance.md)

Geral

* controlar a demanda de recursos ou gerenciar recursos

5. Security

* estudar LGPD
* aceitar termos

6. [Testability](https://github.com/camilaazuma/grupo-estudos/blob/master/quality-attributes/testability.MD)

* definir estrutura de testes já no começo do projeto
    * como será testado
* quais tecnologias serão escolhidas de forma a facilitar testar

7. [Usability](https://github.com/camilaazuma/grupo-estudos/blob/master/quality-attributes/usability.md)

* contratar o Rodrigo
* usuários não podem colocar escalas industriais na receita

## Restrições

**Suposições**

1. Quais dados tem que ser armazenados?

* username, hash senha, email
* receita
    * texto passo a passo
    * avaliação (score + qt de votos)
    * ingredientes (nome + qt)
    * categorias
    * dificuldade (avental arregaçado, by Tig)
    * preparo
    * rendimento
* comentarios

2. Com quais serviços a gente vai integrar?

* oauth - facebook, gmail, ( apple - a ser avaliado, só quando for lançar funcionalidade de rico)

3. Quais serviços têm que ser implementados? 


**Restrições**

1. De que forma temos que nos preocupar com possíveis gargalos? (processamento, acesso ao servidor/banco)

* preocupação com otimização de queries de banco
* se for aplicação mobile, precisaremos de um backend?

2. Demais restrições?
