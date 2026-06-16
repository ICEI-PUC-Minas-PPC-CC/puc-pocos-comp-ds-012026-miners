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

**Conclusão:** A hipótese foi parcialmente confirmada. O modelo manteve desempenho muito parecido com o original, mostrando que o dataset é grande o suficiente para absorver essa mudança sem perda significativa.

---

### Experimento 2 — max_iter=5000

**Hipótese:** Se aumentarmos o número máximo de iterações de 1000 para 5000, o modelo pode melhorar seu desempenho.

| Métrica | Modelo Base | Experimento 2 |
|---|---|---|
| Acurácia | 0.8214 | 0.8252 |
| Precisão | 0.7166 | 0.7233 |
| Recall | 0.4285 | 0.4450 |
| F1-Score | 0.5363 | 0.5510 |

**Conclusão:** A hipótese foi confirmada. Aumentar o max_iter trouxe uma melhora pequena mas consistente em todas as métricas.

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
