# Plano de Testes do Banco de Dados

<span style="color:red">Pré-requisito: <a href="2-Especificação do Projeto.md">Especificação do Projeto</a></span>

Esta seção apresenta os testes realizados no banco de dados desenvolvido pelo grupo. O objetivo é verificar se a estrutura criada atende ao domínio do problema, se as restrições estão corretas e se as consultas SQL produzem os resultados esperados.

Os testes devem demonstrar que o banco de dados foi implementado corretamente, considerando:

- criação das tabelas
- definição das chaves primárias
- definição das chaves estrangeiras
- integridade dos relacionamentos
- inserção de dados
- atualização de registros
- remoção de registros
- execução de consultas SQL
- funcionamento de restrições e validações

---

# Objetivo dos Testes

Os testes têm como objetivo validar a estrutura e o comportamento do banco de dados, verificando se:

- as tabelas foram criadas corretamente
- os relacionamentos entre tabelas estão funcionando
- as restrições impedem dados inválidos
- os dados podem ser inseridos, alterados e removidos corretamente
- as consultas SQL retornam os resultados esperados

---

# Estratégia de Testes

Os testes do banco de dados foram organizados em categorias, permitindo avaliar diferentes aspectos da implementação.

As principais categorias de teste são:

- teste de criação da estrutura
- teste de inserção de dados
- teste de integridade referencial
- teste de atualização de registros
- teste de remoção de registros
- teste de consultas SQL
- teste de restrições e validações

---

# Cenários de Teste

Os cenários a seguir devem ser utilizados para validar o banco de dados.

## Cenário 1 - Criação das tabelas

**Objetivo:** verificar se as tabelas do banco foram criadas corretamente.

**Procedimento:** executar o script de criação do banco de dados.

**Resultado esperado:** todas as tabelas devem ser criadas sem erro, com seus respectivos campos, chaves primárias e chaves estrangeiras.

---

## Cenário 2 - Inserção de registros válidos

**Objetivo:** verificar se o banco permite inserir registros válidos nas tabelas.

**Procedimento:** executar comandos `INSERT` com dados corretos e consistentes com o modelo.

**Resultado esperado:** os registros devem ser inseridos com sucesso.

---

## Cenário 3 - Inserção de registros com chave estrangeira inexistente

**Objetivo:** verificar se o banco impede registros com relacionamento inválido.

**Procedimento:** tentar inserir um registro que referencie uma chave estrangeira inexistente.

**Resultado esperado:** o banco deve impedir a inserção e retornar erro de integridade referencial.

---

## Cenário 4 - Inserção de registros duplicados em chave primária

**Objetivo:** verificar se o banco impede duplicidade de identificadores.

**Procedimento:** tentar inserir dois registros com a mesma chave primária.

**Resultado esperado:** o banco deve rejeitar a segunda inserção.

---

## Cenário 5 - Atualização de registros

**Objetivo:** verificar se os dados podem ser alterados corretamente.

**Procedimento:** executar comandos `UPDATE` em registros existentes.

**Resultado esperado:** os dados devem ser alterados corretamente, respeitando as restrições definidas.

---

## Cenário 6 - Remoção de registros sem dependência

**Objetivo:** verificar se registros sem relacionamento dependente podem ser removidos.

**Procedimento:** executar comando `DELETE` em um registro que não esteja sendo referenciado por outra tabela.

**Resultado esperado:** o registro deve ser removido com sucesso.

---

## Cenário 7 - Remoção de registros com dependência

**Objetivo:** verificar o comportamento da integridade referencial na exclusão.

**Procedimento:** tentar remover um registro que esteja sendo referenciado por outra tabela.

**Resultado esperado:** o banco deve impedir a exclusão, caso a restrição de integridade esteja ativa.

---

## Cenário 8 - Consulta simples

**Objetivo:** verificar se os dados podem ser recuperados corretamente de uma tabela.

**Procedimento:** executar uma consulta `SELECT` simples em uma tabela.

**Resultado esperado:** a consulta deve retornar os registros esperados.

---

## Cenário 9 - Consulta com filtro

**Objetivo:** verificar se os filtros de busca funcionam corretamente.

**Procedimento:** executar uma consulta com cláusula `WHERE`.

**Resultado esperado:** devem ser retornados apenas os registros que atendam à condição.

---

## Cenário 10 - Consulta com JOIN

**Objetivo:** verificar se os relacionamentos entre tabelas podem ser explorados corretamente.

**Procedimento:** executar uma consulta utilizando `JOIN` entre tabelas relacionadas.

**Resultado esperado:** os dados devem ser combinados corretamente conforme o relacionamento definido.

---

## Cenário 11 - Consulta com agregação

**Objetivo:** verificar consultas com funções de agregação.

**Procedimento:** executar consultas com `COUNT`, `SUM`, `AVG`, `MAX` ou `MIN`.

**Resultado esperado:** os valores calculados devem corresponder aos dados armazenados.

---

## Cenário 12 - Teste de campos obrigatórios

**Objetivo:** verificar se campos obrigatórios estão sendo respeitados.

**Procedimento:** tentar inserir registros sem preencher campos definidos como obrigatórios.

**Resultado esperado:** o banco deve impedir a inserção, caso exista restrição correspondente.

---

# Tabela de Casos de Teste

A tabela abaixo pode ser utilizada para registrar os testes executados.

| ID | Caso de Teste | Objetivo | Resultado Esperado | Status |
|---|---|---|---|---|
| CT-01 | Criação das tabelas | Validar estrutura do banco | Tabelas criadas corretamente | Não executado |
| CT-02 | Inserção de dados válidos | Validar inserção | Registros inseridos com sucesso | Não executado |
| CT-03 | Inserção com chave estrangeira inválida | Validar integridade referencial | Inserção rejeitada | Não executado |
| CT-04 | Inserção duplicada de chave primária | Validar unicidade | Inserção rejeitada | Não executado |
| CT-05 | Atualização de registros | Validar alteração de dados | Registro atualizado corretamente | Não executado |
| CT-06 | Remoção sem dependência | Validar exclusão simples | Registro removido | Não executado |
| CT-07 | Remoção com dependência | Validar integridade na exclusão | Exclusão rejeitada | Não executado |
| CT-08 | Consulta simples | Validar recuperação de dados | Registros retornados corretamente | Não executado |
| CT-09 | Consulta com filtro | Validar seleção condicional | Retorno conforme filtro | Não executado |
| CT-10 | Consulta com JOIN | Validar relacionamento entre tabelas | Dados relacionados exibidos corretamente | Não executado |
| CT-11 | Consulta com agregação | Validar cálculos sobre dados | Valores corretos retornados | Não executado |
| CT-12 | Inserção sem campo obrigatório | Validar restrições | Inserção rejeitada | Não executado |

---

# Massa de Dados para Testes

Para execução dos testes, recomenda-se criar uma massa de dados inicial contendo registros suficientes para validar:

- relacionamentos entre tabelas
- consultas simples
- consultas com filtros
- consultas com junção
- funções de agregação

Essa massa de dados pode ser criada por meio de comandos `INSERT`.

---

# Evidências dos Testes

Nesta seção podem ser apresentados:

- comandos SQL executados
- capturas de tela dos resultados
- mensagens de erro esperadas
- saídas das consultas realizadas

As evidências devem demonstrar que os testes foram realmente executados e que o banco apresentou o comportamento esperado.

---

# Ferramentas Utilizadas nos Testes

Os testes podem ser executados em ferramentas como:

- MySQL Workbench
- DBeaver
- pgAdmin
- SQLite Browser
- terminal SQL do SGBD utilizado

Essas ferramentas permitem criar o banco, inserir dados, executar consultas e validar os resultados obtidos.

---

# Considerações Finais

Os testes do banco de dados são importantes para verificar se a estrutura implementada representa corretamente o domínio do problema e se os dados podem ser manipulados de forma consistente e confiável.

A validação por meio desses testes ajuda a garantir que o banco de dados esteja pronto para armazenar, relacionar e recuperar as informações necessárias ao projeto.