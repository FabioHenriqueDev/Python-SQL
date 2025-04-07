# 🧾 Sistema de Controle de Estoque com Interface Gráfica

Este projeto é um sistema de controle de estoque com uma interface gráfica desenvolvida em **Tkinter**, conectado a um banco de dados **SQLite3** por meio da biblioteca **pyodbc**. Ele permite a realização completa das operações de **CRUD** (Criar, Ler, Atualizar e Deletar), de forma simples e interativa.

---

## 🔧 Tecnologias Utilizadas

- **Python 3**
- **SQLite3** (banco de dados local)
- **pyodbc** (conexão entre Python e o banco de dados)
- **Tkinter** (criação da interface gráfica)

---

## 📦 Funcionalidades do Sistema

O sistema foi criado para gerenciar insumos de forma simples e direta. A interface possui campos para preencher os dados do insumo, e botões que acionam cada função.

### ✅ Adicionar Insumo
- Verifica se o insumo já existe no banco (comparando nome e lote).
- Se já existir, atualiza a quantidade somando com a nova entrada.
- Se não existir, insere um novo registro com nome, quantidade, data de validade e lote.

### ❌ Deletar Insumo
- Deleta o insumo do banco de dados com base no nome e lote informados.
- Valida se o insumo existe antes de tentar excluir.

### ➖ Consumir Insumo
- Subtrai uma quantidade específica de um insumo já existente.
- Verifica se o insumo e lote estão cadastrados antes de aplicar a redução.

### 🔍 Visualizar Insumo
- Exibe os dados completos de um insumo (ID, nome, quantidade, data de validade e lote) a partir do nome e do lote informados.
- Mostra os resultados diretamente na interface, em uma área de texto.

---

## 🧠 Lógica por Trás do Sistema

- A interface foi construída com **Tkinter**, incluindo `Entry`, `Text` e `Button`, e imagens personalizadas para uma apresentação mais intuitiva.
- O banco de dados foi criado em SQLite com uma tabela chamada `Estoque`, contendo os seguintes campos:
  - `Id` (INTEGER PRIMARY KEY AUTOINCREMENT)
  - `Produto` (TEXT)
  - `Quantidade` (INTEGER)
  - `DataValidade` (TEXT)
  - `Lote` (INTEGER)

### 🔗 Exemplo de Conexão com o Banco:
```python
dados_conexao = ("Driver={SQLite3 ODBC Driver};Server=localhost;Database=Estoque.db;")
conexao = pyodbc.connect(dados_conexao)
