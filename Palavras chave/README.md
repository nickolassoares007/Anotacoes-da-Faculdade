# 🔠 Sumário de Palavras-Chave

 [A](#a)  [B](#b)  [C](#c)  [D](#d)  [E](#e)  [F](#f)  [G](#g)
 
 [H](#h)  [I](#i)  [J](#j)  [K](#k)  [L](#l)  [M](#m)  [N](#n)
 
 [O](#o)  [P](#p)  [Q](#q)  [R](#r)  [S](#s)  [T](#t)  [U](#u)

 [V](#v)  [W](#w)  [X](#x)  [Y](#y)  [Z](#z)



---


# A

<details><summary>Árvores de decisão</summary>

Uma árvore de decisão é uma estrutura que representa escolhas sucessivas.
Cada nó é um estado possível do problema; cada ramo é uma decisão; cada folha é um resultado final.

Funciona como um mapa de possibilidades: para cada escolha, várias portas se abrem.
É essencial em algoritmos de busca, IA básica, jogos e sistemas de regras.

Na engenharia de software, aparece em:

– busca em grafos  
– lógica de IA  
– parsing de linguagens  
– validação de regras  

Árvores de decisão são a cartografia da incerteza.

</details>

<details><summary>ACID</summary>

ACID é um conjunto de quatro propriedades que garantem que transações em banco de dados sejam confiáveis. Isso impede que dados virem caos quando várias operações acontecem ao mesmo tempo ou quando o sistema falha no meio do caminho.

ACID significa:

- Atomicity: A transação é indivisível. Ou tudo acontece, ou nada acontece. Se o sistema cair depois do primeiro passo, o banco desfaz tudo com um rollback. Nenhuma parte da transação pode ficar “pela metade”.
- Consistency: A transação não pode violar as regras do banco. Antes e depois da transação, o banco precisa continuar válido. Se uma operação quebrar uma regra, a transação é cancelada.
- Isolation: Várias transações podem rodar ao mesmo tempo, mas cada uma deve se comportar como se estivesse sozinha.
- Durability: Depois que a transação recebe commit, o resultado não pode ser perdido.

| Letra | Ideia                         |
| ----- | ----------------------------- |
| A     | tudo ou nada                  |
| C     | nunca quebra regras           |
| I     | transações não se atrapalham  |
| D     | dados confirmados nunca somem |


</details>

<details><summary>ANTLR</summary>
ANother Tool for Language Recognition

É uma ferramenta usada para criar parsers e interpretadores de linguagem.

Traduzindo: é uma ferramenta para construir linguagens de programação ou interpretar estruturas de texto complexas.

</details>

---

# B

---

# C

---

# D

<details><summary>DFS (Depth-First Search)</summary>

DFS é a Busca em Profundidade, usada para percorrer grafos e árvores.

Ela segue um caminho até o fim antes de voltar para tentar outras rotas.
É o motor clássico do backtracking.

Usos comuns:

– backtracking  
– detecção de ciclos  
– ordenação topológica  
– resolver labirintos

</details>

---

# E

---

# F
<details><summary>Full Table Scan</summary>
 
Full Table Scan é quando o banco de dados **precisa ler todas as linhas de uma tabela** para encontrar os dados solicitados.
Isso acontece quando **não existe um índice útil** para a consulta.

</details>

---

# G

---

# H

<details><summary>Heurísticas</summary>

Heurística é uma estratégia inteligente para guiar a busca em direção às opções com maior chance de sucesso.

Não garante a solução ideal, mas economiza tempo.

Em backtracking, heurísticas ajudam a pular caminhos ruins cedo.

Exemplo:  
No problema das N-Rainhas, escolher primeiro posições com menor chance de conflito acelera tudo.

</details>

---

# I

---

# J

---

# K

---

# L

---

# M

---

# N



---

# O

---

# P

<details><summary>Permutações</summary>

Permutações são todas as formas possíveis de reorganizar um conjunto de elementos.

Com 3 letras (A, B, C), formamos seis ordens diferentes.
É puro caos arrumadinho.

Usado em:  
– anagramas  
– testes automatizados  
– criptografia  
– simulações

</details>

<details><summary>Problemas combinatórios</summary>

São problemas que envolvem testar muitas combinações possíveis de escolhas.
O número de possibilidades costuma crescer de forma exponencial.

Exemplos:  
– Sudoku  
– N-Rainhas  
– knapsack  
– subsets  

É o território natural do backtracking.

</details>

---

# Q

---

# R

<details><summary>Recursão</summary>

Recursão ocorre quando uma função chama ela mesma para resolver uma versão menor do mesmo problema.

Lógica fundamental:  
– reduz o problema  
– resolve a parte menor  
– combina  
– para no caso-base

É central em:  
– backtracking  
– divide and conquer  
– árvores  
– grafos

</details>

---

# S

---

# T

<details><summary>Tradeoff de Indexação</summary>


Índices são estruturas usadas para **acelerar consultas** em um banco de dados.  
Eles funcionam como o **índice de um livro**, permitindo encontrar informações rapidamente sem precisar ler toda a tabela.

O problema é que **cada índice precisa ser atualizado sempre que um dado é inserido, alterado ou removido**.

Por isso existe um **tradeoff (equilíbrio)**:

- **Mais índices → consultas (SELECT) mais rápidas**
- **Mais índices → operações de escrita (INSERT, UPDATE, DELETE) mais lentas**

Isso acontece porque o banco precisa **atualizar todas as estruturas de índice** sempre que um dado muda.

### Regra prática
Criar índices principalmente em colunas usadas em:

- `WHERE`
- `JOIN`
- `ORDER BY`

Evitar índices em:

- colunas pouco consultadas
- colunas com poucos valores diferentes (baixa seletividade)

### Resumo

Índices melhoram a **velocidade de leitura**, mas aumentam o **custo de escrita**.  
O objetivo é encontrar um **equilíbrio entre performance de consulta e custo de manutenção dos índices**.

</details>

---

# U

---

# V

---

# W

---

# X

---

# Y

---

# Z
