# SQL Cheatsheet

Este repositório contém uma lista de códigos SQL úteis para consultas, manipulação e gerenciamento de bancos de dados relacionais.

## Conteúdo

1. [Introdução](#introdução)
2. [Comandos Básicos](#comandos-básicos)
3. [Consultas](#consultas)
4. [Manipulação de Tabelas](#manipulação-de-tabelas)
5. [Funções Agregadas](#funções-agregadas)
6. [Subconsultas](#subconsultas)
7. [Procedimentos e Views](#procedimentos-e-views)
8. [Triggers](#triggers)

## Introdução

Este repositório visa fornecer uma referência rápida para os principais comandos SQL utilizados no dia a dia de desenvolvimento e administração de bancos de dados.

## Comandos Básicos

- **SHOW DATABASES;**: Lista todos os bancos de dados disponíveis.
- **USE \<nome_do_banco\>;**: Seleciona um banco de dados específico para uso.
- **SHOW TABLES;**: Exibe todas as tabelas dentro do banco de dados selecionado.

## Consultas

- **SELECT * FROM \<nome_da_tabela\>;**: Seleciona todos os registros de uma tabela.
- **SELECT \<coluna1\>, \<coluna2\> FROM \<nome_da_tabela\>;**: Seleciona colunas específicas de uma tabela.
- **SELECT ... FROM ... WHERE ...;**: Consulta com condições de filtro.

## Manipulação de Tabelas

- **CREATE DATABASE \<nome_do_banco\>;**: Cria um novo banco de dados.
- **CREATE TABLE \<nome_da_tabela\> (...);**: Cria uma nova tabela com colunas especificadas.
- **ALTER TABLE \<nome_da_tabela\> ...;**: Altera a estrutura de uma tabela existente.

## Funções Agregadas

- **MAX(\ <coluna\> );**: Retorna o maior valor de uma coluna.
- **MIN(\ <coluna\> );**: Retorna o menor valor de uma coluna.
- **AVG(\ <coluna\> );**: Retorna a média dos valores de uma coluna.

## Subconsultas

- **SELECT ... WHERE \<coluna\> > (SELECT AVG(\ <coluna\> ) FROM ...);**: Exemplo de subconsulta com filtro.

## Procedimentos e Views

- **Procedimentos**: Os procedimentos são blocos de código SQL nomeados e armazenados no banco de dados que podem ser chamados e executados repetidamente. Eles são úteis para executar operações complexas ou frequentes de forma fácil e eficiente.
- **Views**: As views são consultas SQL predefinidas armazenadas no banco de dados como objetos virtuais. Elas podem ser tratadas como tabelas virtuais e são úteis para simplificar consultas complexas, melhorar a segurança dos dados e reutilizar consultas comuns.

### Exemplo de View

- Criando uma view para mostrar o nome e o salário dos funcionários com salário maior que 5000
  
CREATE VIEW Funcionarios_Salario_Altos AS
SELECT nome, salario
FROM Funcionarios
WHERE salario > 5000

## Triggers

- Triggers: Triggers são procedimentos automáticos que são executados em resposta a eventos específicos, como inserção, atualização ou exclusão de registros em uma tabela. Eles são úteis para aplicar ações automatizadas, como validações de dados, auditorias ou atualizações de informações relacionadas.

Exemplo de Trigger

- Criando um trigger para atualizar a data de modificação de um produto sempre que for atualizado
- 
CREATE TRIGGER AtualizarDataModificacao
BEFORE UPDATE ON Produtos
FOR EACH ROW
BEGIN
    SET NEW.data_modificacao = NOW();
END;

## Conclusão

Esperamos que este repositório seja útil como uma referência rápida para suas consultas e operações em SQL. Sinta-se à vontade para contribuir com mais exemplos e melhorias.
