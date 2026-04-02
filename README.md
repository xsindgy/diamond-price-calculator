# diamond-price-calculator

# 💎 Diamond Filter

Sistema de busca inteligente de diamantes com base no dataset público [Diamonds do Kaggle](https://www.kaggle.com/datasets/shivam2503/diamonds), que contém mais de **53.000 registros reais** com características detalhadas de cada pedra.

---

## 📌 Sobre o Projeto

O usuário informa as características desejadas de um diamante — quilate, corte, cor e pureza — e o sistema retorna os registros mais compatíveis da base de dados. Quando não há correspondência exata, o filtro aplica uma **margem de similaridade progressiva**, garantindo que sempre haja resultados relevantes.

---

## 🔍 Como Funciona

1. **Busca exata** — verifica se existe algum diamante com todas as características idênticas.
2. **Margem progressiva no quilate** — se não encontrar, aumenta a tolerância de ±0.1 até ±1.0 quilate mantendo os demais filtros.
3. **Busca por similaridade** — se ainda assim não houver resultado, relaxa todos os campos e pontua cada registro por número de características coincidentes, retornando os 10 mais próximos.

---

## 🗂️ Dataset

| Atributo | Descrição |
|----------|-----------|
| `carat` | Peso do diamante em quilates |
| `cut` | Qualidade do corte (Fair, Good, Very Good, Premium, Ideal) |
| `color` | Cor (D = incolor até J = leve tonalidade) |
| `clarity` | Pureza (FL, IF, VVS1, VVS2, VS1, VS2, SI1, SI2, I1) |
| `price` | Preço em dólares americanos |
| `x`, `y`, `z` | Dimensões em milímetros |
| `depth` | Profundidade total (%) |
| `table` | Largura do topo relativa ao ponto mais largo (%) |

> Fonte: [Kaggle — Diamonds Dataset por Shivam Agrawal](https://www.kaggle.com/datasets/shivam2503/diamonds)

---

## 🛠️ Tecnologias

- **Python 3**
- **Pandas** — leitura e filtragem do CSV
- **Tabulate** — formatação da tabela de resultados no terminal

---

## ▶️ Como Usar

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/diamond-filter.git
cd diamond-filter
```

### 2. Instale as dependências

```bash
pip install pandas tabulate
```

### 3. Baixe o dataset

Faça o download do arquivo `diamonds.csv` no [Kaggle](https://www.kaggle.com/datasets/shivam2503/diamonds) e coloque na raiz do projeto.

### 4. Execute

```bash
python main.py
```

---

## 💻 Exemplo de Uso

```
=== Filtro de Diamantes ===
Digite o quilate: 1.5
Digite o corte: Ideal
Digite a cor: G
Digite a pureza: VS1

=== Resultados Encontrados ===
 carat    cut color clarity  depth  table  price     x     y     z
  1.50  Ideal     G     VS1   61.5     55   8500  7.32  7.35  4.51
  1.51  Ideal     G     VS1   62.1     56   8750  7.34  7.37  4.57
```

---

## 📁 Estrutura do Projeto

```
diamond-filter/
├── main.py          # Script principal
├── diamonds.csv     # Dataset (baixar do Kaggle)
└── README.md
```

---

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se livre para usar e modificar.
