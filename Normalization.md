Quando tratamos com dados, entender a forma como eles devem se comportar é muito importante para que haja uma fluidez maior. Como tudo na vida, bancos de dados também devem obedecer regras que são importantes para seu funcionamento e entendimento, é por isso que a normalização é muito importante.

# O que é normalização?

É um passo a passo onde vamos analisar atributos de uma entidade com o objetivo de evitar e eliminar alguns problemas que podem ocorrer devido à forma que os dados vão ser tratados.

No processo de normalização de um banco de dados, tratamos as entidades daquele contexto utilizando algumas regras, que são as formas normais. É provável que em outras literaturas possam tratar de cinco formas normais, porém aqui abordaremos as três primeiras, que são as fundamentais e são suficientes.

# Formas normais

Como falado, abordaremos apenas as três primeiras formas normais, que são:

1FN – Primeira Forma Normal.
2FN – Segunda Forma Normal.
3FN – Terceira Forma Normal.

## 1FN

Uma relação está na Primeira Forma Normal quando não existe a repetição de campos que tenha o mesmo valor.

## 2FN

Uma tabela está na Segunda Forma Normal quando está na Primeira Forma Normal e todos os atributos não chave de uma tabela forem dependentes de uma chave primária.

## 3FN

Uma tabela está na Terceira Forma Normal quando está na Segunda Forma Normal e nenhuma coluna não chave depender de outra coluna não chave.

# Aplicando as formas normais

Já sabemos o que cada forma normal diz, agora, como elas são aplicadas?

É simples e basta seguir determinados passos.

## Aplicando a 1FN

1 – Identificar a chave primária da entidade.
2 – Identificar o campo repetido e removê-lo.
3 – Criar uma entidade com a chave primária da entidade anterior e o campo repetido.

## Aplicando a 2FN

1 – Identificar os atributos que não dependem de um atributo chave.
2 – Remover esses atributos da entidade e criar uma com eles.

## Aplicando a 3FN

1 – Identificar todos os atributos que são funcionalmente dependentes de outros não chave.
2 – Removê-los.

# Exemplo prático

Dada a tabela Cliente:

| Id_Cliente    | Nome          | Telefone              | Endereço                        | DDD           |
| ------------- | ------------- | --------------------- | ------------------------------- | ------------- |
| 1             | Pedro         | 98877-5566,98989-9090 | Rua das Rosas, 130 - Vila Verde | 80            |
| 2             | Paulo         | 98855-5454            | Rua Oliveira, 98 - Vila Formoza | 70            |
| 3             | José          | 98770-8080,98770-7656 | Rua Batista, 100 - Vila Verão   | 75            |
| 4             | Maria         | 98888-9999            | Av. Pereira, ap. 40 - Vila Nova | 60            |

## Aplicando a 1FN

### Qual será a chave primária da entidade?

Nesse caso, o recomendado é usar o campo Id_Cliente.

OBS: É muito comum usar a coluna nomeada de ID + Complemento para utilizá-la como chave primária. Esse valor deve ser único para cada registro.

### Algum registro tem mais de um valor para o mesmo campo?

Sim, na coluna Telefone existem registros com mais de um telefone.

### O campo que se repete deve virar uma entidade

Sendo assim criamos uma tabela para armazenar as informações dos telefones e eliminamos essa informação da tabela Cliente.

Agora teremos duas tabelas.

Cliente:

| Id_Cliente    | Nome          | Endereço                        | DDD           |
| ------------- | ------------- | ------------------------------- | ------------- |
| 1             | Pedro         | Rua das Rosas, 130 - Vila Verde | 80            |
| 2             | Paulo         | Rua Oliveira, 98 - Vila Formoza | 70            |
| 3             | José          | Rua Batista, 100 - Vila Verão   | 75            |
| 4             | Maria         | Av. Pereira, ap. 40 - Vila Nova | 60            |

Telefone:

| Id_Cliente    | Telefone      | 
| ------------- | ------------- | 
| 1             | 98877-5566    | 
| 1             | 98989-9090    | 
| 2             | 98855-5454    | 
| 3             | 98770-8080    | 
| 3             | 98770-7656    | 
| 4             | 98888-9999    | 

## Aplicando a 2FN

### Algum atributo não depende do campo chave?

Sim, a coluna DDD não depende do Id_Cliente, ela está relacionada com o telefone.

### É necessário criar outra identidade para colocar a coluna DDD?

Não, como ele está relacionado ao telefone, podemos adicionar o campo DDD na tabela telefone.

Assim teremos duas tabelas.

Cliente:

| Id_Cliente    | Nome          | Endereço                        |
| ------------- | ------------- | ------------------------------- |
| 1             | Pedro         | Rua das Rosas, 130 - Vila Verde |
| 2             | Paulo         | Rua Oliveira, 98 - Vila Formoza |
| 3             | José          | Rua Batista, 100 - Vila Verão   |
| 4             | Maria         | Av. Pereira, ap. 40 - Vila Nova |

Telefone:

| Id_Cliente    | Telefone      | DDD           |
| ------------- | ------------- | ------------- |
| 1             | 98877-5566    | 80            |
| 1             | 98989-9090    | 80            |
| 2             | 98855-5454    | 70            |
| 3             | 98770-8080    | 75            |
| 3             | 98770-7656    | 75            |
| 4             | 98888-9999    | 60            | 
