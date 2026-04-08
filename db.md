---
title: "Banco de dados"
layout: default
---

# Banco de Dados
## Sumário

1. [Banco de dados](#1-banco-de-dados-bd)
- [Modelos de Dados](#11-modelos-de-dados) 
- [Estrutura](#12-estrutura)
- [Arquiteturas](#13-arquiteturas)
2. [Sistemas de gerenciamento de banco de dados](#2-sistema-de-gerenciamento-de-banco-de-dados-sgbd)
- [Visão geral](#21-visão-geral-dos-principais-sgbds)
- [Linguagens](#22-linguagens)
3. [MySQL](#3-mysql)
- [Principais operações em SQL](#31-principais-operações-em-sql)
- [Filtros e operadores](#32-filtros-e-operadores)
- [Relacionamentos](#33-relacionamentos)

## 1. Banco de Dados (BD)

> É uma coleção organizada de dados, tipicamente armazenados e acessíveis eletronicamente.

Sua importância está relacionada à facilidade de organização das informações, ao suporte à tomada de decisões com base em dados e à eficiência e escalabilidade nas operações de negócio.

### 1.1 Modelos de Dados

| Modelo | Organização dos Dados |
|------|------|
| Hierárquico | Estrutura em árvore |
| Rede | Estrutura em grafos |
| Relacional | Estrutura em tabelas |

#### 1.1.1 Modelo Relacional

É um modelo de dados que organiza as informações em **tabelas** (relações). Os principais elementos onde as informações são armazenadas são:

- **Tabelas** ~> Estrutura que armazena os dados
- **Linhas (registros)** ~> Cada linha representa um registro da tabela
- **Colunas (atributos)** ~> Cada coluna representa uma característica do dado

A estrutura de um banco de dados relacional inclui:

- **Chave primária (Primary Key)**  ~> Coluna ou conjunto de colunas que identifica de forma única cada registro em uma tabela.
- **Chave estrangeira (Foreign Key)**  ~> Coluna que cria uma relação entre duas tabelas diferentes, referenciando a chave primária de outra tabela.
- **Índice (Index)** ~> Estrutura utilizada para melhorar a velocidade das consultas realizadas na tabela.

### 1.2 Estrutura

- **Esquema (Schema)** ~> É a estrutura lógica de um banco de dados que define como os dados são organizados e como eles se relacionam.

### 1.3 Arquiteturas

1. **Monolítica** ~> Todos os dados e serviços estão centralizados em um único sistema.
2. **Cliente-Servidor** ~> Os dados ficam armazenados em servidores e são acessados por aplicações clientes.
3. **Distribuída** ~> Os dados são armazenados em múltiplos sistemas interconectados.

## 2. Sistema de Gerenciamento de Banco de Dados (SGBD)

> É um software responsável pela criação, gerenciamento e manipulação das informações armazenadas em um banco de dados.

Entre suas principais funções estão:

- Controle de concorrência (gerenciamento de múltiplos acessos simultâneos ao banco)
- Recuperação de falhas
- Segurança dos dados
- Garantia da integridade das informações

Alguns dos SGBDs mais populares são:

- MySQL
- PostgreSQL
- Oracle
- SQL Server

### 2.1 Visão geral dos principais SGBDs

- **MySQL** – Open Source e amplamente utilizado em aplicações web.
- **PostgreSQL** – Suporte a tipos de dados complexos e grande extensibilidade.
- **Oracle** – Alta performance e segurança, muito utilizado em grandes empresas.
- **SQL Server** – Sistema da Microsoft integrado a diversas ferramentas corporativas.

### 2.2 Linguagens

As principais linguagens utilizadas em bancos de dados são:

- **DDL (Data Definition Language)**  ~> Utilizada para criar e modificar a estrutura do banco de dados.
  
  **Exemplos:**
  - CREATE
  - ALTER
  - DROP

- **DML (Data Manipulation Language)** ~> Utilizada para manipular os dados armazenados. 
  
    **Exemplos:**
    - INSERT
    - UPDATE
    - DELETE
    - SELECT

## 3. MySQL

- **MySQL Workbench** ~> Ferramenta gráfica (GUI) utilizada para modelagem de banco de dados, desenvolvimento de consultas SQL e administração de servidores.

### 3.1 Principais operações em SQL

1. **INSERT** – Inserir dados  
2. **SELECT** – Consultar dados  
3. **UPDATE** – Atualizar dados  
4. **DELETE** – Remover dados

### 3.2 Filtros e operadores 

1. **WHERE**
```sql
SELECT * FROM usuarios WHERE idade > 18;
```

2. **AND / OR**
```sql
SELECT * FROM usuarios WHERE idade > 18 AND nome = 'Miguel';
```

3. **LIKE**
```sql
SELECT * FROM usuarios WHERE nome LIKE 'M%';
```

### 3.3 Relacionamentos

Relacionamentos definem como tabelas se conectam. É aqui que o banco deixa de ser “ilhas de dados” e vira uma rede inteligente.

**Tipos principais**

*1:1 (Um para um)*
- Um registro em uma tabela se relaciona com apenas um em outra
- Ex: Usuário ↔ Perfil

*1:N (Um para muitos)*
- Um registro pode se relacionar com vários outros
- Ex: Usuário → Pedidos

*N:N (Muitos para muitos)*
- Vários registros se relacionam com vários outros
- Ex: Alunos ↔ Cursos
- Necessita de uma tabela intermediária (tabela associativa)

**Exemplo de tabela intermediária:**
*Tabela: aluno_curso*

|aluno_id | curso_id
|1 | 2|
|1 | 3|


**Chaves:**

As chaves são os elementos que garantem organização, identificação e relacionamento dentro do banco de dados.

*Chave Primária (Primary Key)*

É a coluna (ou conjunto de colunas) que identifica unicamente cada registro de uma tabela.

Características:
- Não pode se repetir
- Não pode ser nula (NULL)
- Cada tabela deve ter apenas uma chave primária

Exemplo:
```sql
CREATE TABLE usuarios (
  id INT PRIMARY KEY,
  nome VARCHAR(100)
);
```
Aqui, o id funciona como o “CPF” do registro

*Chave Estrangeira (Foreign Key)*

É a coluna que cria uma ligação entre duas tabelas.
Ela aponta para a chave primária de outra tabela.

Exemplo:
```sql
CREATE TABLE pedidos (
  id INT PRIMARY KEY,
  usuario_id INT,
  FOREIGN KEY (usuario_id) REFERENCES usuarios(id)
);
```

Características: 

- usuario_id guarda o ID do usuário
- Ele conecta pedido → usuário

Sem chave estrangeira:

- Você pode ter pedidos sem usuário 

Com chave estrangeira:

- O banco garante integridade 

**Integridade Referencial**

É a regra que garante que os dados estão corretamente conectados.

Exemplo:

- Não pode existir um usuario_id = 99 se o usuário 99 não existe

O banco bloqueia esse erro automaticamente

**Ações com FOREIGN KEY**

Você pode definir o que acontece quando um dado relacionado é alterado:

```sql
FOREIGN KEY (usuario_id) REFERENCES usuarios(id)
ON DELETE CASCADE
```

Tipos comuns:

- **CASCADE** → apaga tudo relacionado
- **SET NULL** → deixa o valor nulo
- **RESTRICT** → impede exclusão

**Chave Composta**

É quando usamos mais de uma coluna como chave primária.

Exemplo:

```sql
CREATE TABLE aluno_curso (
  aluno_id INT,
  curso_id INT,
  PRIMARY KEY (aluno_id, curso_id)
);
```

Aqui, a combinação dos dois IDs é única

**Resumão das chaves**

- Primary Key → identifica
- Foreign Key → conecta
- Integridade → protege os dados

**JOIN (juntar tabelas)**
É o coração dos relacionamentos. Permite consultar dados de várias tabelas ao mesmo tempo.

*INNER JOIN (interseção)*

```sql
SELECT usuarios.nome, pedidos.id
FROM usuarios
INNER JOIN pedidos ON usuarios.id = pedidos.usuario_id;
```
Retorna apenas quem tem correspondência nas duas tabelas

*LEFT JOIN (tudo da esquerda)*
```sql
SELECT usuarios.nome, pedidos.id
FROM usuarios
LEFT JOIN pedidos ON usuarios.id = pedidos.usuario_id;
```
Retorna todos os usuários, mesmo sem pedidos

### 3.4 Normalização (conceito essencial)
Normalizar é organizar os dados para evitar repetição e inconsistência.

Objetivos:

- Evitar dados duplicados
- Melhorar organização
- Facilitar manutenção

Exemplo ruim:

|nome | curso|
|Miguel| ADS|
|Miguel| SI|

Melhor:

- tabela alunos
- tabela cursos
- tabela relacionamento
