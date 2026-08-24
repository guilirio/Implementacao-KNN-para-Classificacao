# Trabalho Prático 01 — Classificação KNN

**GCC 128 — Inteligência Artificial**
Prof. Ahmed Ali Abdalla Esmin — Universidade Federal de Lavras (UFLA)

## Descrição

Implementação do algoritmo **K-Nearest Neighbors (KNN)** do zero (*hardcore*),
sem utilizar bibliotecas que já contenham o algoritmo implementado, e posterior
comparação com a implementação da biblioteca **Scikit-learn**.

O objetivo é fixar os conceitos de classificação supervisionada vistos em aula,
avaliando o classificador com diferentes valores de `k` e comparando as métricas
de avaliação entre a implementação própria e a de terceiros.

## Base de dados

Utiliza-se a base **Iris**, carregada a partir de um **arquivo CSV** (obtido no
Kaggle). A leitura via CSV mantém o pipeline desacoplado da fonte de dados,
permitindo reutilizar o algoritmo com outras bases tabulares no futuro
(features numéricas + uma coluna de classe).

A base Iris contém 150 amostras divididas em 3 classes (*setosa*, *versicolor*,
*virginica*), com 4 atributos cada: comprimento e largura da sépala e da pétala.

## Estrutura do notebook

O notebook (`knn_trabalho.ipynb`) está dividido nas seguintes etapas, cada uma
com sua própria célula de markdown explicativa:

| Célula | Etapa | Descrição |
|--------|-------|-----------|
| 1 | Preparação | Imports e configuração do ambiente |
| 2 | Tratamento dos dados | Leitura do CSV e separação em 70% treino / 30% teste |
| 3 | Treino | Definição do classificador KNN e armazenamento dos dados de treino |
| 4 | Predição pontual | Seleção aleatória de uma amostra de teste para verificação |
| 5 | Resultados e acurácia | Taxa de reconhecimento para `k = {1, 3, 5, 7}`, matriz de confusão e métricas |
| 6 | Comparação | Implementação com Scikit-learn e comparação das métricas |

> **Observação sobre o KNN:** por ser um algoritmo *lazy* (preguiçoso), o KNN não
> possui uma fase de treino que ajusta parâmetros — a etapa de "treino" consiste
> apenas em **armazenar** os dados. Todo o cálculo ocorre no momento da predição.

## O que é implementado "do zero"

Na versão *hardcore*, são implementados manualmente:

- Separação treino/teste (*split* 70/30)
- Cálculo de distância (euclidiana)
- Busca dos `k` vizinhos mais próximos
- Votação majoritária
- Matriz de confusão
- Métricas de avaliação: **precisão, revocação e acurácia**

O **Scikit-learn** é utilizado **exclusivamente na Célula 6**, para comparação.

## Dependências

- Python 3.x
- `numpy` — estruturas de dados e operações matemáticas
- `pandas` — leitura e tratamento do CSV
- `matplotlib` — visualização (matriz de confusão)
- `scikit-learn` — utilizado **apenas** na etapa de comparação

Instalação:

```bash
pip install numpy pandas matplotlib scikit-learn
```

## Como executar

1. Baixe a base Iris (CSV) do Kaggle e coloque-a na pasta do projeto.
2. Ajuste o caminho do arquivo na Célula 2, se necessário.
3. Abra o notebook e execute as células na ordem (1 → 6).

```bash
jupyter notebook knn_trabalho.ipynb
```

## Reprodutibilidade

Uma *seed* fixa (`SEED = 42`) é utilizada no embaralhamento dos dados, garantindo
que o split treino/teste e os resultados sejam reproduzíveis entre execuções.

## Entrega

- Código da aplicação (`.ipynb`)
- Relatório de até 1 página (`.pdf`) com a comparação entre as implementações e
  a análise de desempenho (conclusão)

## Autores

- Nome 1
- Nome 2
