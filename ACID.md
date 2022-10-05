# O que é ACID?

No português: Atomicidade, Consistência, Isolamento e Durabilidade.

No inglês: Atomicity, Consistency, Isolation and Durability.

É o conjunto de propriedades de um banco de dados transacional.

## O que é um banco de dados transacional e uma transação?

No contexto de banco de dados, uma transação é uma sequência de operações, logo um banco de dados transacional é um banco onde ocorrem transações.

## Explicando cada propriedades

### Atomicidade (Atomicity)

A transação deve ser executada totalmente ou não ser executada, jamais deve existir uma execução parcial.

### Consistência (Consistency)

A transação cria um novo estado válido dos dados ou retorna todos os dados ao seu estado anterior, antes da transação ter sido iniciada.

###Isolamento (Isolation)

Se existe mais de uma transação em andamento, uma não pode interferir no resultado da outra.

Durabilidade (Durability)

Os dados validados devem ser registrados pelo sistema e mesmo que haja falha no sistema, os dados devem estar dispostos no estado correto.

## Qual a importância da ACID?

A ACID garante o correto funcionamento de um banco de dados, impedindo que dados sejam corrompidos ou perdidos no processamento das transações. Em outras palavras, para manter a integridade de um banco de dados, é muito importante respeitar essas propriedades.
