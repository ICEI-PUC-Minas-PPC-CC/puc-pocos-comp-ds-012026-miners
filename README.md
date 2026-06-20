# Dataset: Predição de Faixa Salarial


`CURSO` Ciência da Computação

`DISCIPLINA` Data Science e Big Data

`SEMESTRE` 4º Período

`TEMA` Predição de Faixa Salarial

O dataset contém informações socioeconômicas de indivíduos e tem como objetivo prever se uma pessoa possui renda superior ou inferior a US$50.000 anuais.

---

## Integrantes

* Aline Maria de Miranda Pereira
* Ellen Stefany da Silva 
* Liz Rosa Nguyen 
* Nicole Cristina dos Santos  

---

## Orientador

* Diego Roberto Gonçalves de Pontes
	  
---

# Pesquisa

A estrutura científica do projeto está organizada na pasta:

➡ `01_pesquisa/`

Sugere-se a seguinte ordem de leitura:

1. `01_objetivos.md`  
2. `02_questoes_pesquisa.md`  
3. `03_protocolo.md`  
4. `04_hipoteses.md`  
5. `05_busca/`  
6. `06_selecao/`  
7. `07_artigos/`  
8. `08_sintese/`  

Esta seção contém:

- definição do problema  
- objetivos da pesquisa  
- questões de investigação  
- protocolo metodológico  
- estratégia de busca  
- critérios de seleção  
- base de artigos analisados  
- síntese dos resultados  

---

# Dados

O conjunto de dados utilizados neste trabalho foi o dataset Adult Income, disponível na plataforma Kaggle. Ele tem como base da dados o Censo dos Estados Unidos de 1994 e foi desenvolvido por Barry Becker e Ronny Kohavi. Ele contém aproximadamente **48 mil registros** e reúne características socioeconômicas da população, que permitem investigar fatores que podem influenciar o nível de renda dos indivíduos. 

As variáveis trabalhadas neste dataset são as seguintes: 

| nome original no dataset | nome adotado no trabalho | descrição |
| :---: | :---: | :---: |
| age | idade | idade do indivíduo |
| workclass | classe_de_trabalho | tipo de vínculo empregatício |
| fnlwgt | peso_amostral | peso estatístico atribuído pelo censo |
| education | escolaridade | nível de escolaridade do indivíduo |
| educational-num | anos_de_escolaridade | escolaridade representada numericamente |
| marital-status | estado_civil | situação conjjugal do indivíduo |
| occupation | ocupacao | profissão ou área de atuação |
| relationship | relacao_familiar | relação do indivíduo dentro da família |
| race | raca | grupo racial declarado |
| gender | sexo | sexo do indivíduo |
| capital-gain | ganho_capital | ganhos obtidos |
| capital-loss | perda_capital | perdas financeiras |
| hour-per-week | horas_semana | quantidade média de horas trabalhadas na semana |
| native-country | pais_de origem | país de origem do indivíduo |
| income | renda | faixa de renda anual (variável alvo) |

É possível observar uma amostra dos dados em: 

➡ `02_dados/amostras/amostra.md`

---

# Análise e Exploração

A seguir, estão dispostas as estatísticas descritivas das variáveis quantitativas do conjunto de dados. Foram observadas medidas de tendência central (média e mediana), de dispersão (desvio-padrão) e de amplitude (máximo e mínimo), permitindo visualizar a variabilidade de cada atributo. 

| Variável | Média | Mediana | Mínimo | Máximo | Desvio padrão |
|:---|---:|---:|---:|---:|---:|
| idade | 38.64 | 37.00 | 17 | 90 | 13.71 |
| peso_amostral | 189664.13 | 178144.50 | 12285 | 1490400 | 105604.03 |
| anos_de_escolaridade | 10.08 | 10.00 | 1 | 16 | 2.57 |
| ganho_capital | 1079.07 | 0.00 | 0 | 99999 | 7452.02 |
| perda_capital | 87.50 | 0.00 | 0 | 4356 | 403.00 |
| horas_semana | 40.42 | 40.00 | 1 | 99 | 12.39 |

É possível observar os gráficos resultantes da análise e exploração em:

➡ `07_resultados/tabelas`

---

# Código

A implementação principal do projeto está em:

➡ `04_codigo/`

Organização:

- `configuracao/` → parâmetros e caminhos do projeto  
- `dados/` → carregamento e pré-processamento  
- `modelos/` → treinamento, avaliação e inferência  
- `utilitarios/` → funções auxiliares  
- `execucao/` → pipeline principal  

---

# Experimentos

Os experimentos conduzidos estão em:

➡ `05_experimentos/`

Cada experimento deve conter:

- configuração utilizada  
- resultados obtidos  
- logs de execução  

Importante:

- não sobrescrever experimentos  
- manter rastreabilidade  

---

# Modelos Treinados

Os artefatos gerados no treinamento estão em:

➡ `06_modelos_treinados/`

Observações:

- registrar versão, parâmetros e origem  
- evitar versionamento de arquivos muito grandes, se necessário  

---

# Resultados

As saídas finais do projeto estão em:

➡ `07_resultados/`

Organização:

- `figuras/`  
- `tabelas/`  
- `relatorios/`  

---

# Documentação

Materiais complementares e o artigo estão em:

➡ `08_documentacao/`

Conteúdo:

- `artigo.tex` → estrutura do artigo científico  
- `manual.md` → instruções e observações técnicas  

---

# Testes

Os testes do projeto estão em:

➡ `09_testes/`

Objetivo:

- garantir consistência do código  
- validar funcionamento das rotinas  

---

# Observações

Este repositório foi estruturado com foco em:

- organização científica  
- reprodutibilidade  
- separação entre pesquisa e implementação  
- rastreabilidade de experimentos  

Substituir os textos iniciais conforme a evolução do projeto.
