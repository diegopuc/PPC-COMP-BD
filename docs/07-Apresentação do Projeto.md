# Apresentação do Projeto

<span style="color:red">Pré-requisito: Todos os demais artefatos do projeto</span>

Esta seção descreve a apresentação final do projeto de banco de dados desenvolvido pelo grupo.

A apresentação deve sintetizar os principais artefatos produzidos ao longo do projeto, incluindo:

- contexto do problema
- domínio de dados analisado
- modelagem conceitual (MER)
- modelo lógico
- modelo físico
- implementação do banco de dados
- exemplos de consultas SQL
- resultados dos testes realizados

O objetivo da apresentação é demonstrar como o banco de dados foi projetado e implementado para representar corretamente o domínio do problema.

A apresentação deve ser entregue em formato **PowerPoint ou PDF**.

---

# Título do Projeto

Apresente o nome do projeto e, se desejado, um nome para o banco de dados desenvolvido.

Exemplo:

**Sistema de Gestão de Biblioteca – Projeto de Banco de Dados**

Inclua também:

- nome da disciplina
- nome do professor
- nomes dos integrantes do grupo
- semestre ou período letivo

---

# Identidade Visual

Os slides devem manter uma identidade visual consistente, utilizando:

- cores coerentes com o tema do projeto
- imagens ou ícones relacionados ao domínio do problema
- diagramas claros e legíveis
- fontes de fácil leitura

Evite excesso de texto nos slides. Utilize diagramas, tabelas e exemplos para facilitar a compreensão da estrutura do banco de dados.

> **Links Úteis**
> - https://rockcontent.com/blog/design-para-slides/
> - https://www.shutterstock.com/pt/blog/7-dicas-de-design-para-criar-apresentacoes-de-powerpoint-incriveis-e-eficientes
> - https://soap.com.br/blog/especialista-do-ted-da-10-dicas-para-criar-slides-eficazes-e-bonitos

---

# Estrutura Sugerida da Apresentação

A apresentação deve conter uma sequência lógica que mostre a evolução do projeto.

## Slide 1 – Capa

- nome do projeto  
- disciplina  
- professor  
- integrantes do grupo  

---

## Slide 2 – Contexto do Problema

Apresentar o domínio do problema escolhido.

Exemplo:

- sistema de biblioteca
- sistema de vendas
- sistema de clínica
- sistema de eventos
- sistema acadêmico

Explique brevemente quais informações precisam ser organizadas nesse domínio.

---

## Slide 3 – Objetivo do Projeto

Apresentar o objetivo do projeto de banco de dados.

Exemplo:

Desenvolver um banco de dados relacional capaz de organizar e relacionar as informações do domínio escolhido, permitindo armazenamento estruturado e consultas eficientes.

---

## Slide 4 – Levantamento das Informações

Apresentar as principais informações identificadas no domínio.

Exemplo:

- clientes
- produtos
- pedidos
- pagamentos

Essas informações darão origem às entidades do banco de dados.

---

## Slide 5 – Modelo Entidade-Relacionamento (MER)

Apresentar o diagrama MER desenvolvido pelo grupo.

Explicar brevemente:

- entidades
- relacionamentos
- cardinalidades

---

## Slide 6 – Modelo Lógico

Apresentar a transformação do MER para o modelo relacional.

Mostrar as tabelas principais do banco de dados.

Exemplo:

Cliente  
Produto  
Pedido  
Item_Pedido

---

## Slide 7 – Modelo Físico

Apresentar a estrutura final das tabelas.

Mostrar exemplos de:

- chaves primárias
- chaves estrangeiras
- tipos de dados

---

## Slide 8 – Implementação do Banco

Apresentar exemplos de comandos SQL utilizados para criar o banco.

Exemplo:

```sql
CREATE TABLE cliente (
    id_cliente INT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100)
);