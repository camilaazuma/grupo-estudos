## API

USER (stand-by)

- cadastro
    - email
    - senha
        - validação
    - username
- login

RECEITA

- (adicionar imagens no modelo)
- lista
    - filtros: nome, ingredientes, da receita, qt do ingrediente, categoria
    - retornos: lista de receitas
        - score, difficulty_rate, spent_time, servings
    - paginado
- detalhe
    - parametro: id
    - retornos: 1 receita
        - todas as colunas da receita
        - user: username
        - lista de ingredientes
        - lista de categorias
        - lista de passos
- cadastro
- edição
    - campo a campo
- deleção da receita

(obs: ver como funciona atualização de entidade para 1 campo ou n campos)

SCORE
- GET
- POST
    - ID usuário
    - ID da receita
    - nota de 1 a 5

COMENTÁRIO

- lista de comentários
    - filtro: ID da receita
    - order: recente
    - paginado
- cadastro do comentário
- deletação

UNIDADES

- conversão (GET)
    - parametro: unidade, qt
    - lista opções de unidades já com a qt associada

INGREDIENTES

- conversão (GET)
    - parametro: ingrediente, qt
    - lista opções de ingredientes já com a qt associada
