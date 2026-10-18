## Tech Challenge — Fase 2 | POSTECH Data Analytics

### 1. Identificação

<table>
<tr><th>Campo</th><th>Valor</th></tr>
<tr><td>Turma</td><td>15DTAT</td></tr>
<tr><td>Grupo</td><td>3</td></tr>
<tr><td>Data de entrega</td><td>11/03/2026</td></tr>
</table>

#### Integrantes

<table>
<tr><th>Nome completo</th><th>RM</th><th>E-mail</th></tr>
<tr><td>Gabriel Alves da Silva</td><td>1</td><td>gasmeas10@gmail.com</td></tr>
<tr><td>Dimitria Doi</td><td>2</td><td>dimitria.ro@gmail.com</td></tr>
<tr><td>Breno Plada Delege</td><td>3</td><td>brenoplada@gmail.com</td></tr>
<tr><td>Yan Souza Montes</td><td>4</td><td>yansouzamontes@hotmail.com</td></tr>
</table>

### 2. Links da entrega

(Conteúdo original mantido)

### 3. O problema

A avaliação sensorial de vinhos depende da disponibilidade de especialistas experientes, o que pode tornar o processo demorado, caro e sujeito a variações entre avaliadores. Além disso, reunir um painel de especialistas para analisar grandes volumes de amostras nem sempre é viável. Nesse contexto, o uso de características físico-químicas do vinho, associado a técnicas de machine learning, permite prever sua qualidade de forma rápida e consistente. Essa abordagem reduz a dependência de avaliações humanas, aumenta a velocidade de análise e possibilita decisões mais eficientes na classificação de vinhos.

#### Variável alvo

A variável alvo definida foi a coluna Quality, pois representa a qualidade do vinho. Com base nas características físico-químicas, o modelo de machine learning consegue aprender padrões e prever a qualidade de novos vinhos.

#### Dataset

Fonte: https://www.kaggle.com/datasets/yasserh/wine-quality-dataset

Linhas × colunas: 1143 × 13

Período / versão: 1

### 4. Como reproduzir

(Conteúdo original mantido)

### 5. Resultados

| Modelo | Acurácia | Precisão | Recall | F1 | AUC-ROC |
|----------|----------|----------|----------|----------|----------|
| Regressão Logística | 0.74 | 0.31 | 0.81 | 0.45 | 0.88 |
| Árvore de Decisão | 0.74 | 0.32 | 0.46 | 0.46 | 0.83 |
| Random Forest | 0.84 | 0.43 | 0.43 | 0.50 | 0.87 |

**Modelo escolhido:** Random Forest.

O modelo escolhido foi o Random Forest, pois apresentou os melhores resultados entre os modelos avaliados. Seu desempenho superior está relacionado à combinação de múltiplas árvores de decisão, permitindo maior capacidade de generalização e previsões mais próximas da realidade.

**Métricas priorizadas:** Acurácia, F1-Score e AUC-ROC.
