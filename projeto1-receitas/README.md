# Receitas de comidas e drinks dados os ingredientes que tem na cozinha

## Casos de uso

**Escopo**

* Usuário pesquisa por receita
    * filtrando pelo nome da receita
    * filtrando pelos ingredientes na receita, incluindo a quantidade máxima dos itens
* Usuário preenche a lista de ingredientes que tem em casa com speech to text
* Usuário comenta na receita
* Usuário cadastra receita dentro do sistema usando texto manual / speech to text
* Usuário cadastra receita dentro do sistema usando foto do livro da vó do Ricardo, com IA pra reconhecer a receita
* Usuário edita receita própria / propõe edição de receita de outro usuário (PR)
    * Receita é versionada
* Usuário cria um fork da receita
* Sistema encontra ingredientes substitutos para as receitas (e fala para o usuário com a voz da bela gil)
* Sistema atualiza a lista de ingredientes que tem na casa do usuário quando ele faz uma compra em site de mercado
* Sistema sugere receitas personalizadas de acordo com o histórico de ingredientes do usuário
* Sistema sugere compras de mercado a partir de ingredientes que liberariam receitas próximas das que o usuário costuma fazer
* Sistema exibe calorias de cada ingrediente na receita

**Fora do escopo**

* Usuário se cadastra no sistema
* Usuário faz login no sistema
* Usuário configura visibilidade da receita
* Usuário favorita receitas

## Atributos de qualidade

1. Availability

Geral

* o sistema pode ter 2 estados:
	* processando (trabalhando na requisição)
	* bloqueado (incapaz de responder por estar):
		* aguardando recurso (quando um recurso pode ser usado por um client por vez
		* disponibilidade: algum recurso pode estar indisponível ou offline
		* dependencia de outros serviços (precisa esperar resposta de outro serviço)

2. Interoperability

Geral

* Quais são os sistemas (serviços, SO, hardware) integrados e qual a interface entre eles
	* Possibilidade de sistemas futuros integrarem

3. Modifiability

Geral

* Podem ocorrer mudanças no hardware, SO, sistemas interoperáveis, na performance do sistema, na qt de usuários etc
	* Se nem todas as responsabilidades do módulo são alteradas em uma mudança hipotética, talvez elas não devessem estar nesse módulo
* Quais mudanças devem ser suportadas?
* Parametrização


4. [Performance](https://github.com/camilaazuma/grupo-estudos/blob/master/quality-attributes/performance.md)

Geral

* controlar a demanda de recursos ou gerenciar recursos

5. Security

Considerações

* estudar LGPD

6. [Testability](https://github.com/camilaazuma/grupo-estudos/blob/master/quality-attributes/testability.MD)

Geral

* capacidade de detectar erros rapidamente através de testes

7. [Usability](https://github.com/camilaazuma/grupo-estudos/blob/master/quality-attributes/usability.md)

Geral

* quão fácil e intuitivo é para o usuário utilizar o sistema, bem como o suporte que o sistema fornece ao usuário

## Restrições

**Suposições**


**Restrições**