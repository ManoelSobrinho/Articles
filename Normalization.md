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
2 – Identificar o campo repetido e removê-lo
3 – Criar uma entidade com a chave primária da entidade anterior e o campo repetido.

## Aplicando a 2FN

1 – Identificar os atributos que não dependem de um atributo chave.
2 – Remover esses atributos da entidade e criar uma com eles.

## Aplicando a 3FN

1 – Identificar todos os atributos que são funcionalmente dependentes de outros não chave.
2 – Removê-los.

# Exemplo prático

Dada a tabela Cliente:

| Id_Cliente    | Nome          | Telefone      | Endereço      |
| ------------- | ------------- | ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |
