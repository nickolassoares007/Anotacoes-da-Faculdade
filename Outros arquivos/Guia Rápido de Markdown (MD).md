# 📘 Guia Rápido de Markdown (MD)

Este é um resumo das funções mais importantes do Markdown para criar anotações limpas, organizadas e fáceis de ler no GitHub.

---

<!-- É dessa maneira que se coloca um comentário de invisvel que não vai ser visto no markdown -->

## 🏷 Títulos

```md

Use `#` para criar títulos e subtítulos.

# Título 1
## Título 2
### Título 3
#### Título 4

```
<!-- Depois de usar o ```md no começo da seção que você quer marcar, use no final ``` para fechar -->

## ✍️ Ênfase (itálico e negrito)

- *itálico*
- **negrito**
- ***negrito + itálico***

## 📌 Listas
Lista não ordenada

- Item 1
- Item 2
  - Subitem

Lista ordenada

1. Primeiro
2. Segundo
3. Terceiro

## 🔗 Links

[Texto do link](https://meulink.com)

📁 Links internos (para pastas e arquivos no GitHub)

- [Arquitetura de Computadores](Arquitetura%20de%20computadores/)
- [Resumo de Algoritmos](resumo-algoritmos.md)

🖼 Imagens

![Imagem teste](https://m.media-amazon.com/images/S/pv-target-images/81ef275effa427553a847bc220bebe1dc314b2e79d00333f94a6bcadd7cce851._SX1080_FMjpg_.jpg)

##📦 Blocos de código

Use a função `print()` para exibir valores.

Bloco com linguagem (para highlight no GitHub)

```python
def soma(a, b):
    return a + b
```
---

## 🧱 Citações

> Isso é uma citação.
> Pode ter várias linhas.

## 📊 Tabelas

| Disciplina | Status |
|-----------|--------|
| Algoritmos | ✔️ |
| Arquitetura | ✔️ |
| Redes | ❌ |

## 🧩 Separadores
---

## 🔄 Checklists

- [x] Estudar algoritmos
- [ ] Revisar arquitetura
- [ ] Subir arquivos no GitHub

## 🎨 Blocos informativos

> **Nota:** Isso é importante.
> **Atenção:** Isso requer cuidado.

## 🗺 Diagramas Mermaid (renderizam direto no GitHub)

```mermaid
flowchart TD
    A[Início] --> B[Processo]
    B --> C[Fim]
```
