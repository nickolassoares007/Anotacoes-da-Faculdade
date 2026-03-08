# DDL — Data Definition Language

## O que é

**DDL (Data Definition Language)** é o conjunto de comandos SQL responsáveis por **criar, modificar e remover estruturas do banco de dados**.

Essas estruturas incluem:

- bancos de dados
- tabelas
- colunas
- índices
- constraints (restrições)
- schemas

Ou seja, o DDL define **a arquitetura do banco de dados**.

---

# Principais conceitos do DDL (Data Definition Language)

- Restrições - Constraint
- Regras de Nomeação
- índices
- views
- schemas
- Data Type (Tipo de dado)
- Cardinality (Cardinalidade)
- Relationship (Relacionamento)


---

# Principais comandos DDL

## CREATE

Usado para **criar estruturas no banco de dados**.

Pode criar:

- banco de dados
- tabelas
- índices
- views
- schemas

### Exemplo criando uma tabela

```sql
CREATE TABLE usuarios (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100),
    idade INT
);
````

Aqui estamos definindo:

* estrutura da tabela
* tipos de dados
* chave primária

---

## ALTER

Usado para **modificar estruturas existentes**.

Pode:

* adicionar colunas
* remover colunas
* modificar tipos de dados
* adicionar restrições

### Adicionando uma coluna

```sql
ALTER TABLE usuarios
ADD telefone VARCHAR(20);
```

### Alterando tipo de dado

```sql
ALTER TABLE usuarios
ALTER COLUMN idade BIGINT;
```

---

## DROP

Remove completamente uma estrutura do banco.

⚠️ Cuidado: normalmente **remove tudo permanentemente**.

### Exemplo

```sql
DROP TABLE usuarios;
```

Isso remove:

* a tabela
* todos os dados
* índices
* relações

---

## TRUNCATE

Remove **todos os registros de uma tabela**, mas **mantém a estrutura**.

É mais rápido que `DELETE`.

### Exemplo

```sql
TRUNCATE TABLE usuarios;
```

Diferença importante:

| Comando  | O que remove          |
| -------- | --------------------- |
| DELETE   | registros específicos |
| TRUNCATE | todos os registros    |
| DROP     | tabela inteira        |

---

# Principais objetos criados com DDL

## Tabelas

Estruturas que armazenam dados.

```sql
CREATE TABLE produtos (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    preco DECIMAL(10,2)
);
```

---

## Índices

Estruturas usadas para **acelerar consultas**.

```sql
CREATE INDEX idx_nome
ON usuarios(nome);
```

Índices funcionam como **índice de um livro**.

---

## Constraints (restrições)

Regras que garantem **integridade dos dados**.

Principais:

### PRIMARY KEY

Identifica registros únicos.

```sql
id INT PRIMARY KEY
```

---

### FOREIGN KEY

Cria relação entre tabelas.

```sql
FOREIGN KEY (usuario_id)
REFERENCES usuarios(id)
```

---

### NOT NULL

Impede valores nulos.

```sql
nome VARCHAR(100) NOT NULL
```

---

### UNIQUE

Impede valores duplicados.

```sql
email VARCHAR(100) UNIQUE
```

---

### CHECK

Define uma condição para os dados.

```sql
idade INT CHECK (idade >= 18)
```

---

### DEFAULT

Define valor padrão.

```sql
status VARCHAR(20) DEFAULT 'ativo'
```

---

# Quando usar DDL

| Situação               | Comando         |
| ---------------------- | --------------- |
| Criar tabela           | CREATE          |
| Criar banco            | CREATE DATABASE |
| Adicionar coluna       | ALTER           |
| Modificar coluna       | ALTER           |
| Criar índice           | CREATE INDEX    |
| Apagar tabela          | DROP            |
| Limpar dados da tabela | TRUNCATE        |

---

# Características importantes do DDL

### 1. Afeta a estrutura do banco

DDL altera **o modelo de dados**, não os registros.

---

### 2. Normalmente executa commit automático

Em muitos bancos (MySQL, PostgreSQL, Oracle), comandos DDL:

* executam automaticamente
* não podem ser revertidos com `ROLLBACK`

---

### 3. Impacta performance

Alterar estrutura pode:

* reconstruir tabelas
* recriar índices
* bloquear acesso temporariamente

---

# Resumo mental rápido

DDL controla **a estrutura do banco**.

Principais comandos:

* CREATE → criar estrutura
* ALTER → modificar estrutura
* DROP → remover estrutura
* TRUNCATE → limpar dados da tabela

```

Agora uma curiosidade que muda bastante a visão de quem trabalha com banco.

Em sistemas grandes (Netflix, bancos, redes sociais), **DDL é tratado quase como engenharia civil**. Alterar uma tabela gigante pode travar sistemas inteiros. Por isso existem técnicas como:

- **migrations versionadas**
- **blue-green schema changes**
- **expand and contract migrations**

Essas técnicas surgiram no mundo de engenharia de dados moderna, muito usadas por empresas como :contentReference[oaicite:0]{index=0} e :contentReference[oaicite:1]{index=1} para evitar downtime.

Uma provocação interessante para quem está estudando banco de dados:

> Um programador escreve código todos os dias.  
> Um engenheiro de software projeta **estruturas que vão durar anos**.

DDL está nesse segundo grupo.

Existe ainda um conceito extremamente importante que quase sempre aparece junto de DDL quando você começa a trabalhar profissionalmente:

**Database Migrations** (Flyway, Liquibase, Prisma, etc.).

É basicamente **versionamento de estrutura de banco**, quase como Git para schema. Quando você entende isso, começa a enxergar banco de dados como parte do sistema, não apenas armazenamento.
```
