## 1. Conceitos iniciais

**SQL (Structured Query Language)** é a linguagem usada para **criar, manipular, consultar e controlar bancos de dados relacionais**.

Ela trabalha com alguns conceitos fundamentais:

* **Database (Banco de dados)** → conjunto de tabelas
* **Tabela (Table)** → estrutura que armazena dados
* **Coluna (Column)** → atributo da tabela
* **Linha (Row / Record)** → registro da tabela
* **Chave primária (Primary Key)** → identifica unicamente um registro
* **Chave estrangeira (Foreign Key)** → cria relação entre tabelas
* **Registro (tuplas)** → entradas individuais em uma tabela que contêm informações específicas relacionadas a uma entidade

Exemplo de tabela `usuarios`:

| id | nome | email                                   |
| -- | ---- | --------------------------------------- |
| 1  | Ana  | [ana@email.com](mailto:ana@email.com)   |
| 2  | João | [joao@email.com](mailto:joao@email.com) |

---

# 2. Organização da SQL

Os comandos SQL são geralmente divididos em **5 categorias**.

## DQL — Data Query Language

Comandos para **consultar dados**.

Principal comando:

* `SELECT`

---

## DML — Data Manipulation Language

Manipula dados dentro das tabelas.

Principais comandos:

* `INSERT`
* `UPDATE`
* `DELETE`

---

## DDL — Data Definition Language

Define a **estrutura do banco de dados**.

Principais comandos:

* `CREATE`
* `ALTER`
* `DROP`
* `TRUNCATE`

---

## DCL — Data Control Language

Controla **permissões de acesso**.

Principais comandos:

* `GRANT`
* `REVOKE`

---

## DTL / TCL — Transaction Control Language

Controla **transações no banco de dados**.

Principais comandos:

* `COMMIT`
* `ROLLBACK`
* `SAVEPOINT`

---

# 3. Principais comandos

## SELECT

Consulta dados em uma tabela.

```sql
SELECT nome, email
FROM usuarios;
```

Consultar todos os campos:

```sql
SELECT * FROM usuarios;
```

---

## INSERT

Insere novos registros.

```sql
INSERT INTO usuarios (nome, email)
VALUES ('Carlos', 'carlos@email.com');
```

---

## UPDATE

Atualiza dados existentes.

```sql
UPDATE usuarios
SET email = 'novo@email.com'
WHERE id = 1;
```

⚠️ O `WHERE` é importante para evitar alterar todos os registros.

---

## DELETE

Remove registros.

```sql
DELETE FROM usuarios
WHERE id = 1;
```

---

## CREATE

Cria estruturas no banco (tabelas, bancos etc.).

```sql
CREATE TABLE usuarios (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100)
);
```

---

## ALTER

Altera estrutura de uma tabela.

```sql
ALTER TABLE usuarios
ADD telefone VARCHAR(20);
```

---

## DROP

Remove completamente uma estrutura.

```sql
DROP TABLE usuarios;
```

---

## TRUNCATE

Remove **todos os dados da tabela**, mas mantém a estrutura.

```sql
TRUNCATE TABLE usuarios;
```

---

## COMMIT

Confirma uma transação.

```sql
COMMIT;
```

---

## ROLLBACK

Desfaz alterações da transação atual.

```sql
ROLLBACK;
```

---

# 4. Quando usar cada comando (exemplos)

| Situação                          | Comando    |
| --------------------------------- | ---------- |
| Consultar dados                   | `SELECT`   |
| Inserir novos registros           | `INSERT`   |
| Atualizar informações             | `UPDATE`   |
| Apagar registros específicos      | `DELETE`   |
| Criar tabelas ou banco            | `CREATE`   |
| Modificar estrutura da tabela     | `ALTER`    |
| Excluir tabela ou banco           | `DROP`     |
| Limpar todos os dados da tabela   | `TRUNCATE` |
| Confirmar alterações da transação | `COMMIT`   |
| Desfazer alterações               | `ROLLBACK` |
| Dar permissões de acesso          | `GRANT`    |
| Remover permissões                | `REVOKE`   |

---
