# Predição de Faixa Salarial

## Integrantes
- Aline Maria de Miranda Pereira
- Ellen Stefany da Silva
- Liz Rosa Nguyen
- Nicole Cristina dos Santos

## Orientador
- Diego Roberto Gonçalves de Pontes

---

## 1. Sobre o Dataset

| | |
|---|---|
| **Nome** | Adult Income Dataset |
| **Link** | https://www.kaggle.com/datasets/wenruliu/adult-income-dataset |
| **Registros** | 48.842 |
| **Atributos** | 15 |
| **Variável-alvo** | renda (income) |
| **Tipo do problema** | Classificação |

**Contexto:** O dataset contém informações socioeconômicas de indivíduos e tem como objetivo prever se uma pessoa possui renda superior ou inferior a US$50.000 anuais.

---

## 2. Análise Estatística

| Variável | Média | Mediana | Mínimo | Máximo | Desvio Padrão |
|---|---|---|---|---|---|
| Idade | 38.64 | 37.00 | 17 | 90 | 13.71 |
| Anos de Escolaridade | 10.08 | 10.00 | 1 | 16 | 2.57 |
| Ganho de Capital | 1079.07 | 0.00 | 0 | 99999 | 7452.02 |
| Perda de Capital | 87.50 | 0.00 | 0 | 4356 | 403.00 |
| Horas por Semana | 40.42 | 40.00 | 1 | 99 | 12.39 |

### Distribuição da Variável-Alvo
- **<=50K:** 37.155 registros (76,07%)
- **>50K:** 11.687 registros (23,93%)

**Observação:** O dataset é desbalanceado. A grande maioria das pessoas, cerca de 76%, ganha abaixo de 50K, enquanto apenas 24% ganham acima. Essa diferença pode influenciar o modelo, que tende a acertar mais facilmente quem ganha menos por ser a categoria mais comum nos dados.

---

## 3. Principais Observações dos Gráficos

**Renda por Gênero:** A maioria dos registros do dataset são de homens. Além disso, a proporção de homens que ganham acima de 50K é bem maior do que a de mulheres, mostrando uma diferença significativa entre os gêneros na faixa salarial mais alta.

**Escolaridade x Renda:** Quanto mais anos de estudo, maior a chance de ganhar acima de 50K. Pessoas com mais escolaridade aparecem com mais frequência na faixa salarial mais alta.

**Idade x Renda:** O gráfico mostra que as pessoas que ganham acima de 50K tendem a ter uma idade maior. A concentração de renda mais alta aparece a partir dos 30 anos, enquanto os mais jovens, por volta dos 20 anos, estão majoritariamente na faixa abaixo de 50K.

---

## 4. Preparação dos Dados

Antes da aplicação do modelo, foi realizado o pré-processamento dos dados. Foi feita uma cópia dos dados originais para que não fossem alterados.

A variável-alvo renda foi convertida para representações numéricas binárias:
- 0 → renda anual menor ou igual a 50K
- 1 → renda anual superior a 50K

Nas demais variáveis categóricas foi empregada a técnica de Label Encoding, que atribui um identificador numérico para cada categoria existente em uma variável.

---

## 5. Modelo Utilizado

**Nome:** Regressão Logística

**Objetivo:** Classificar se uma pessoa ganha acima ou abaixo de 50K, com base nas suas informações pessoais como idade, escolaridade e ocupação.

**Como funciona:** Esse modelo lê as informações de uma pessoa e calcula as chances dela ganhar acima ou abaixo de 50K. Internamente ele transforma esses dados em um número entre 0 e 1. Se esse número passar de 0,5 o modelo classifica como acima de 50K, se não, classifica como abaixo.

**Por que escolhemos:** Escolhemos esse modelo porque o nosso problema tinha só duas respostas possíveis: ganha acima ou abaixo de 50K. Além disso ele é fácil de interpretar e de explicar.

---

## 6. Execução Inicial — Modelo Base

| Métrica | Valor |
|---|---|
| Acurácia | 0.8214 |
| Precisão | 0.7166 |
| Recall | 0.4285 |
| F1-Score | 0.5363 |

---

## 7. Experimentos

### Experimento 1 — Divisão 70/30

**Hipótese:** Se diminuirmos a quantidade de dados para treino, mudando a divisão de 80/20 para 70/30, as métricas podem apresentar pequenas variações.

| Métrica | Modelo Base | Experimento 1 |
|---|---|---|
| Acurácia | 0.8214 | 0.8219 |
| Precisão | 0.7166 | 0.7134 |
| Recall | 0.4285 | 0.4405 |
| F1-Score | 0.5363 | 0.5447 |

Neste experimento foi utilizado o algoritmo de **Regressão Logística** para realizar uma classificação dos dados. Para isso, o conjunto de dados foi dividido em duas partes: **70% para treinamento** e **30% para teste**.

A etapa de treinamento foi realizada utilizando 70% dos dados disponíveis, permitindo que o modelo aprendesse os padrões existentes no conjunto. Em seguida, os 30% restantes foram utilizados para testar o desempenho do modelo em dados que ele não havia visto anteriormente.

Após o treinamento, foram calculadas algumas métricas para avaliar a qualidade das previsões realizadas pelo modelo.

### Resultados Obtidos

- **Acurácia:** 82,19%
- **Precisão:** 71,34%
- **Recall:** 44,05%
- **F1-Score:** 54,47%

### Análise dos Resultados

A **acurácia** de 82,19% indica que o modelo acertou a maioria das classificações realizadas no conjunto de teste. Esse resultado mostra que, de forma geral, o modelo apresentou um bom desempenho.

A **precisão** de 71,34% demonstra que, quando o modelo classificou um caso como positivo, ele acertou essa previsão na maior parte das vezes.

Já o **recall** apresentou valor de 44,05%, indicando que o modelo encontrou menos da metade dos casos positivos existentes no conjunto de teste. Isso significa que alguns exemplos positivos não foram identificados corretamente.

O **F1-Score**, que combina precisão e recall em uma única métrica, foi de 54,47%. Esse valor mostra que existe um desequilíbrio entre essas duas métricas, principalmente devido ao recall mais baixo.

### Conclusão

Os resultados mostram que a Regressão Logística conseguiu atingir uma boa taxa de acertos gerais, representada pela acurácia de 82,19%. No entanto, o modelo ainda apresenta dificuldades para identificar todos os casos positivos, como pode ser observado pelo valor do recall.
De maneira geral, o experimento demonstrou que o modelo possui um desempenho satisfatório, mas ainda há espaço para melhorias visando aumentar a identificação correta dos casos positivos e melhorar o equilíbrio entre as métricas de avaliação.

---

### Experimento 2 — max_iter=5000

**Hipótese:** Se aumentarmos o número máximo de iterações de 1000 para 5000, o modelo pode melhorar seu desempenho.

| Métrica | Modelo Base | Experimento 2 |
|---|---|---|
| Acurácia | 0.8214 | 0.8252 |
| Precisão | 0.7166 | 0.7233 |
| Recall | 0.4285 | 0.4450 |
| F1-Score | 0.5363 | 0.5510 |

Neste experimento foi utilizado o mesmo algoritmo de **Regressão Logística**, porém aumentando o parâmetro `max_iter` de 1000 para 5000. Esse parâmetro define o número máximo de iterações que o algoritmo pode executar durante o treinamento para encontrar a melhor solução.

O objetivo deste teste foi verificar se permitir mais iterações poderia melhorar o desempenho do modelo. Para manter uma comparação justa com o Experimento 1, foram utilizados os mesmos conjuntos de treinamento e teste.

Após o treinamento, o modelo foi avaliado utilizando as métricas de acurácia, precisão, recall e F1-Score.

### Resultados Obtidos

- **Acurácia:** 82,52%
- **Precisão:** 72,33%
- **Recall:** 44,50%
- **F1-Score:** 55,10%

### Análise dos Resultados

A **acurácia** aumentou levemente para 82,52%, indicando uma pequena melhora na quantidade total de classificações corretas realizadas pelo modelo.

A **precisão** passou para 72,33%, mostrando que o modelo ficou um pouco mais confiável ao classificar casos positivos.

O **recall** também apresentou uma pequena melhora, atingindo 44,50%. Apesar do aumento, o modelo ainda deixa de identificar uma parcela significativa dos casos positivos existentes.

O **F1-Score** subiu para 55,10%, refletindo o ganho observado tanto na precisão quanto no recall.

### Comparação com o Experimento 1

Ao comparar os resultados dos dois experimentos, observa-se que o aumento do parâmetro `max_iter` trouxe uma melhora discreta em todas as métricas avaliadas.

| Métrica | Experimento 1 | Experimento 2 |
|----------|----------|----------|
| Acurácia | 82,19% | 82,52% |
| Precisão | 71,34% | 72,33% |
| Recall | 44,05% | 44,50% |
| F1-Score | 54,47% | 55,10% |

### Conclusão

Os resultados mostram que aumentar o número máximo de iterações permitiu que o algoritmo encontrasse uma solução ligeiramente melhor, resultando em pequenos ganhos em todas as métricas avaliadas. No entanto, as diferenças foram relativamente pequenas, indicando que o modelo já estava próximo da convergência no Experimento 1.

Dessa forma, embora o aumento de `max_iter` tenha gerado uma melhora no desempenho, o impacto foi limitado. Para obter ganhos mais significativos, pode ser necessário explorar outras estratégias, como ajustes de hiperparâmetros, seleção de atributos ou utilização de algoritmos diferentes.

---

### Experimento 3 — 8 Atributos Principais

**Hipótese:** Se utilizarmos apenas 8 variáveis, o modelo pode manter um desempenho semelhante ao modelo original.

| Métrica | Modelo Base | Experimento 3 |
|---|---|---|
| Acurácia | 0.8214 | 0.8214 |
| Precisão | 0.7166 | 0.7121 |
| Recall | 0.4285 | 0.4348 |
| F1-Score | 0.5363 | 0.5399 |

**Conclusão:** A hipótese foi validada. Utilizando apenas 8 variáveis, o modelo manteve desempenho semelhante ao original. As 5 variáveis eliminadas eram dispensáveis para a predição salarial.

---

## 8. Comparativo Geral

| Experimento | Acurácia | F1-Score |
|---|---|---|
| Baseline (80/20) | 0.8214 | 0.5363 |
| Exp 1 - Divisão 70/30 | 0.8219 | 0.5447 |
| Exp 2 - max_iter=5000 | 0.8252 | 0.5510 |
| Exp 3 - 8 atributos | 0.8214 | 0.5399 |

---

## 9. Conclusão

O modelo de Regressão Logística foi eficaz para prever a faixa salarial, acertando cerca de 82% das previsões. O experimento 2 obteve melhor resultado com max_iter=5000, pois apresentou o maior F1-Score de 0.5510. O projeto mostrou que variáveis como escolaridade, ocupação e estado civil são fundamentais para a previsão salarial. Apesar do bom desempenho, o modelo apresentou dificuldades em identificar corretamente as pessoas que ganham acima de 50K.

---
## Vídeo de apresentação: https://sgapucminasbr.sharepoint.com/sites/DataScience_88e4d4/Documentos%20Compartilhados/General/Recordings/Exibir%20Apenas/Reuni%C3%A3o%20em%20General-20260619_203831-Grava%C3%A7%C3%A3o%20de%20Reuni%C3%A3o.mp4?csf=1&web=1&e=5gqZqo&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D
