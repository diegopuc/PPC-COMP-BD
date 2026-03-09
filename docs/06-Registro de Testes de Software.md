# Registro de Testes do Banco de Dados

<span style="color:red">Pré-requisitos: <a href="8-Plano de Testes de Software.md">Plano de Testes do Banco de Dados</a></span>

Este documento apresenta o registro da execução dos testes realizados no banco de dados desenvolvido pelo grupo. Os testes foram realizados com base no plano de testes previamente definido, com o objetivo de verificar se a estrutura do banco e as consultas SQL funcionam conforme esperado.

Durante os testes foram avaliados:

- criação das tabelas
- inserção de dados
- integridade referencial
- restrições de chave primária
- restrições de chave estrangeira
- atualização de registros
- remoção de registros
- consultas SQL

Os resultados apresentados nesta seção demonstram o comportamento do banco de dados diante das operações executadas.

---

# Execução dos Testes

A tabela a seguir apresenta o registro dos testes executados.

| ID | Caso de Teste | Procedimento | Resultado Esperado | Resultado Obtido | Status |
|---|---|---|---|---|---|
| CT-01 | Criação das tabelas | Executar script de criação do banco | Tabelas criadas sem erro | Tabelas criadas corretamente | OK |
| CT-02 | Inserção de dados válidos | Executar INSERT com dados corretos | Registro inserido | Registro inserido com sucesso | OK |
| CT-03 | Inserção com chave estrangeira inválida | Inserir registro com FK inexistente | Inserção rejeitada | Banco retornou erro de integridade | OK |
| CT-04 | Inserção duplicada de chave primária | Inserir dois registros com mesma PK | Inserção rejeitada | Banco rejeitou duplicidade | OK |
| CT-05 | Atualização de registros | Executar UPDATE | Registro atualizado | Registro atualizado corretamente | OK |
| CT-06 | Remoção de registros | Executar DELETE | Registro removido | Registro removido corretamente | OK |
| CT-07 | Consulta simples | SELECT em tabela | Dados retornados | Dados exibidos corretamente | OK |
| CT-08 | Consulta com JOIN | SELECT com JOIN entre tabelas | Dados relacionados retornados | Consulta executada corretamente | OK |
| CT-09 | Consulta com agregação | SELECT com COUNT ou SUM | Valor agregado correto | Resultado correto | OK |

---

# Exemplos de Testes Executados

## Teste de Inserção

```sql
INSERT INTO cliente (id_cliente, nome, email)
VALUES (1, 'João Silva', 'joao@email.com');