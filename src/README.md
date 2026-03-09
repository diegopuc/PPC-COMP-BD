# Instruções de Utilização

Este diretório contém os arquivos necessários para criação e utilização
do banco de dados do projeto.

O objetivo deste conjunto de arquivos é permitir que qualquer pessoa
consiga recriar o banco de dados, inserir dados de teste e executar
consultas SQL desenvolvidas no projeto.

------------------------------------------------------------------------

# Ambiente Recomendado

Para execução do banco de dados recomenda-se o seguinte ambiente:

-   **SGBD:** MySQL Server\
-   **Cliente SQL:** MySQL Workbench ou DBeaver\
-   **Sistema Operacional:** Windows, Linux ou macOS

Essas ferramentas permitem executar scripts SQL, visualizar tabelas e
testar consultas de forma simples.

------------------------------------------------------------------------

# Instalação do Ambiente

## Instalar o MySQL Server

Baixe o MySQL no site oficial:

https://dev.mysql.com/downloads/

Durante a instalação configure:

-   usuário `root`
-   senha de acesso ao banco de dados

------------------------------------------------------------------------

## Instalar um Cliente SQL

Para manipulação do banco recomenda-se:

**MySQL Workbench**

https://dev.mysql.com/downloads/workbench/

ou

**DBeaver**

https://dbeaver.io/download/

Essas ferramentas permitem executar scripts SQL e visualizar os dados
armazenados nas tabelas.

------------------------------------------------------------------------

# Criação do Banco de Dados

O banco de dados pode ser criado executando o script presente neste
diretório.

Arquivo:

    create_database.sql

Esse script contém:

-   criação do banco de dados
-   criação das tabelas
-   definição de chaves primárias
-   definição de chaves estrangeiras

## Passos

1.  Abrir o cliente SQL (MySQL Workbench ou DBeaver)
2.  Conectar ao servidor MySQL
3.  Abrir o arquivo `create_database.sql`
4.  Executar o script

Após a execução, todas as tabelas do projeto serão criadas.

------------------------------------------------------------------------

# Inserção de Dados de Teste

Para facilitar testes e consultas, o projeto inclui um script com dados
de exemplo.

Arquivo:

    insert_data.sql

Esse script contém comandos `INSERT` para popular o banco de dados.

## Passos

1.  Abrir o arquivo `insert_data.sql`
2.  Executar o script no cliente SQL

Após isso, o banco estará populado com dados para testes.

------------------------------------------------------------------------

# Execução de Consultas

As consultas SQL desenvolvidas no projeto podem ser encontradas no
diretório:

    consultas/

Esses arquivos contêm exemplos de consultas como:

-   consultas simples (`SELECT`)
-   consultas com filtros (`WHERE`)
-   consultas com junções (`JOIN`)
-   consultas com agregação (`COUNT`, `SUM`, `AVG`)

Exemplo de consulta:

``` sql
SELECT nome
FROM cliente;
```

Exemplo com relacionamento entre tabelas:

``` sql
SELECT c.nome, p.data_pedido
FROM cliente c
JOIN pedido p
ON c.id_cliente = p.id_cliente;
```

------------------------------------------------------------------------

# Estrutura do Diretório

Este diretório está organizado da seguinte forma:

    src/

    create_database.sql
    insert_data.sql

    consultas/
        consultas_basicas.sql
        consultas_avancadas.sql

Descrição:

-   **create_database.sql** -- script de criação do banco de dados
-   **insert_data.sql** -- script de inserção de dados de teste
-   **consultas/** -- consultas SQL desenvolvidas no projeto

------------------------------------------------------------------------

# Execução dos Testes

Para validar o funcionamento do banco de dados recomenda-se executar:

1.  criação das tabelas
2.  inserção de dados de teste
3.  execução das consultas presentes na pasta `consultas`

Esses passos permitem verificar:

-   integridade das tabelas
-   funcionamento das chaves estrangeiras
-   comportamento das consultas SQL

------------------------------------------------------------------------

# Histórico de Versões

### \[0.1.0\] - DD/MM/AAAA

#### Adicionado

-   script de criação do banco de dados
-   script de inserção de dados
-   consultas SQL de exemplo
