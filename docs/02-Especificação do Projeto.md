# Especificação do Domínio de Dados

<span style="color:red">Pré-requisito: <a href="1-Documentação de Contexto.md">Documentação de Contexto</a></span>

Esta seção apresenta a descrição do domínio do problema sob a perspectiva dos dados. O objetivo é compreender quais informações precisam ser armazenadas, como elas se relacionam e como podem ser consultadas.

A partir dessa análise serão construídos os seguintes artefatos do projeto:

- levantamento das informações do domínio
- identificação de entidades e atributos
- identificação dos relacionamentos entre entidades
- construção do Modelo Entidade-Relacionamento (MER)
- transformação para modelo lógico relacional
- definição do modelo físico
- implementação do banco de dados em SQL
- criação de consultas SQL para exploração dos dados

---

# Domínio do Problema

Descreva o contexto do problema escolhido pelo grupo.

Explique qual é o ambiente onde os dados são gerados e utilizados. O objetivo é compreender quais informações existem no domínio e como elas são utilizadas.

Alguns exemplos de domínios possíveis:

- sistema de biblioteca
- sistema de controle de estoque
- sistema de gestão acadêmica
- sistema de pedidos de uma loja
- sistema de clínica médica
- sistema de eventos
- sistema de streaming de música ou filmes

A descrição deve apresentar:

- quais informações existem nesse domínio
- quem utiliza essas informações
- quais decisões dependem desses dados
- quais problemas ocorrem quando os dados não estão organizados

---

# Levantamento das Informações

Nesta seção devem ser identificadas as principais informações existentes no domínio do problema.

O objetivo é levantar **quais dados precisam ser armazenados no banco**.

Exemplo de perguntas que podem ajudar:

- Quais objetos ou elementos existem no sistema?
- Quais informações descrevem esses objetos?
- Que registros precisam ser mantidos ao longo do tempo?
- Quais informações precisam ser consultadas com frequência?

Exemplo (domínio de biblioteca):

Informações importantes:

- livros
- autores
- editoras
- usuários
- empréstimos
- devoluções

Essas informações posteriormente darão origem às **entidades do banco de dados**.

---

# Identificação de Entidades

As entidades representam os principais objetos do domínio que precisam ser armazenados no banco de dados.

Liste as entidades identificadas no domínio.

Exemplo:

| Entidade | Descrição |
|--------|--------|
| Cliente | Pessoa que realiza compras |
| Produto | Item disponível para venda |
| Pedido | Registro de uma compra realizada |
| Pagamento | Informação sobre o pagamento do pedido |

Nesta etapa o objetivo é identificar **quais objetos precisam existir no banco de dados**.

---

# Identificação de Atributos

Cada entidade possui características ou propriedades chamadas **atributos**.

Liste os atributos de cada entidade.

Exemplo:

### Cliente
- id_cliente
- nome
- email
- telefone
- data_cadastro

### Produto
- id_produto
- nome
- preço
- quantidade_estoque

### Pedido
- id_pedido
- data_pedido
- valor_total

Os atributos servirão como base para a definição das colunas das tabelas.

---

# Identificação de Relacionamentos

Nesta seção devem ser identificadas as relações existentes entre as entidades.

Perguntas que ajudam nesta etapa:

- um cliente pode realizar quantos pedidos?
- um pedido possui quantos produtos?
- um produto pode aparecer em quantos pedidos?

Exemplo:

| Entidades | Relacionamento |
|---------|-------------|
| Cliente e Pedido | um cliente pode realizar vários pedidos |
| Pedido e Produto | um pedido pode conter vários produtos |

Essas relações serão representadas posteriormente no **Modelo Entidade-Relacionamento (MER)**.

---

# Modelo Entidade-Relacionamento (MER)

Nesta seção deverá ser apresentado o diagrama MER do sistema.

O diagrama deve representar:

- entidades
- atributos
- relacionamentos
- cardinalidades

Ferramentas sugeridas para construção do MER:

- brModelo
- draw.io
- Lucidchart
- MySQL Workbench
- diagrams.net

Exemplo de inserção do diagrama no documento:

![MER](img/mer.png)

---

# Modelo Lógico

A partir do MER deve ser criado o **modelo lógico relacional**.

Nesta etapa:

- entidades tornam-se tabelas
- atributos tornam-se colunas
- identificadores tornam-se chaves primárias
- relacionamentos tornam-se chaves estrangeiras

Exemplo:

### Cliente

| Campo | Tipo |
|------|------|
| id_cliente | INT |
| nome | VARCHAR |
| email | VARCHAR |
| telefone | VARCHAR |

### Pedido

| Campo | Tipo |
|------|------|
| id_pedido | INT |
| data_pedido | DATE |
| id_cliente | INT |

---

# Modelo Físico

O modelo físico define como o banco de dados será implementado em um SGBD específico.

Nesta etapa devem ser definidos:

- tipos de dados
- chaves primárias
- chaves estrangeiras
- restrições
- estrutura das tabelas

Ferramentas possíveis:

- MySQL
- PostgreSQL
- SQLite
- MariaDB

---

# Implementação do Banco de Dados

Nesta seção devem ser apresentados os scripts SQL utilizados para criação da estrutura do banco de dados.

Exemplo:

```sql
CREATE TABLE cliente (
    id_cliente INT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100),
    telefone VARCHAR(20)
);