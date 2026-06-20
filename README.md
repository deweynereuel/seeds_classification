# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
  <a href="https://www.fiap.com.br/">
    <img src="assets/logo-fiap.png" alt="FIAP Logo" width="40%">
  </a>
</p>

<br>


# Seeds — Classificação de Grãos de Trigo


> Aplicação da metodologia **CRISP-DM** para classificar variedades de grãos de trigo com base em características físicas, utilizando o **Seeds Dataset** da UCI Machine Learning Repository.

---
## 👨‍🎓 Integrantes

- **Jeliel Cardoso** — [LinkedIn](https://www.linkedin.com/in/jelielcardoso/)
- **Denis Paulo Dias da Silva** — [LinkedIn](https://www.linkedin.com/in/denispaulodiassilva/)
- **Deweyne Reuel** — [LinkedIn](https://www.linkedin.com/in/deweyne-reuel-0695522a8/)
- **Matheus Nascimento** — [LinkedIn](https://www.linkedin.com/in/mathnascimento/)

## 👩‍🏫 Professores

- **Tutor(a):** [Sabrina Otoni](https://www.linkedin.com/in/sabrina-otoni-22525519b/)
- **Coordenador(a):** [André Godoi](https://www.linkedin.com/in/andregodoichiovato/)

---

## 📌 Objetivo

Em cooperativas agrícolas de pequeno porte, a classificação dos grãos é realizada manualmente por especialistas — um processo sujeito a erros e demoras. Com o avanço do aprendizado de máquina, é possível **automatizar essa classificação**, aumentando a eficiência e a precisão.

Este projeto desenvolve e compara modelos capazes de identificar automaticamente três variedades de trigo (**Kama**, **Rosa** e **Canadian**) a partir de 7 atributos geométricos do grão.

---

## 📂 Estrutura do Repositório

```
seeds-classification/
│
├── FASE_4
│     └──CTWP
│         └──Cap3
│             └──seeds_classificacao_trigo.ipynb   # Notebook principal (todas as etapas)
└── README.md                                      # Este arquivo
```

---

## 🗃️ Dataset

**Seeds Dataset** — UCI Machine Learning Repository  
🔗 https://archive.ics.uci.edu/ml/datasets/seeds

| Atributo | Descrição |
|---|---|
| `area` | Área da superfície do grão |
| `perimetro` | Comprimento do contorno do grão |
| `compacidade` | Calculada como `4πA/P²` |
| `comprimento_nucleo` | Comprimento do eixo principal da elipse equivalente |
| `largura_nucleo` | Comprimento do eixo secundário da elipse |
| `coeficiente_assimetria` | Medida de assimetria do grão |
| `comprimento_sulco` | Comprimento do sulco central do grão |
| `variedade` *(alvo)* | Kama (1), Rosa (2), Canadian (3) |

- **210 amostras** — 70 por classe (balanceado)
- **Sem valores nulos**

---

## ⚙️ Metodologia — CRISP-DM

```
Entendimento     →   Pré-processamento   →   Modelagem
do Negócio           e EDA                   e Comparação
                                                  ↓
                 Interpretação           ←   Otimização
                 dos Resultados              de Hiperparâmetros
```

---

## 🔬 Etapas do Projeto

### 1. Análise Exploratória (EDA)
- Estatísticas descritivas gerais e por variedade
- Histogramas e boxplots por classe
- Heatmap de correlação entre atributos
- Pairplot para análise de separabilidade
- Detecção de outliers pelo método IQR
- Normalização com `StandardScaler`

### 2. Modelos de Classificação
Divisão dos dados: **70% treino / 30% teste** com estratificação.

| Algoritmo | Biblioteca |
|---|---|
| K-Nearest Neighbors (KNN) | `sklearn.neighbors` |
| Support Vector Machine (SVM) | `sklearn.svm` |
| Random Forest | `sklearn.ensemble` |
| Naive Bayes | `sklearn.naive_bayes` |
| Logistic Regression | `sklearn.linear_model` |

Métricas avaliadas: **Acurácia**, **Precisão**, **Recall**, **F1-Score** e **Matriz de Confusão**.

### 3. Otimização de Hiperparâmetros
| Modelo | Técnica |
|---|---|
| KNN | Grid Search |
| SVM | Grid Search |
| Random Forest | Randomized Search |

### 4. Interpretação e Insights
- Ranking final de todos os modelos
- Análise das features mais importantes (Random Forest)
- Conclusões contextualizadas para o problema real

---

## 🛠️ Tecnologias

- `Python 3.10+`
- `pandas` · `numpy`
- `matplotlib` · `seaborn`
- `scikit-learn`
- `scipy`
- Google Colab

---

## ▶️ Como Executar

1. Acesse [Google Colab](https://colab.research.google.com)
2. Vá em **Arquivo → Fazer upload de notebook**
3. Selecione o arquivo `seeds_classificacao_trigo.ipynb`
4. Execute as células em ordem (Ctrl+F9 para rodar tudo)

> O dataset é carregado automaticamente da UCI — nenhum download manual necessário.

---

