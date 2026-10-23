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

<table>
<tr><th>Item</th><th>Link</th></tr>
<tr><td>Repositório</td><td></td></tr>
<tr><td>Vídeo executivo (≤ 5 min)</td><td></td></tr>
<tr><td>Apresentação</td><td>t.</td></tr>
</table>

### 3. O problema

A avaliação sensorial de vinhos depende da disponibilidade de especialistas experientes, o que pode tornar o processo demorado, caro e sujeito a variações entre avaliadores. Além disso, reunir um painel de especialistas para analisar grandes volumes de amostras nem sempre é viável. Nesse contexto, o uso de características físico-químicas do vinho, associado a técnicas de machine learning, permite prever sua qualidade de forma rápida e consistente. Essa abordagem reduz a dependência de avaliações humanas, aumenta a velocidade de análise e possibilita decisões mais eficientes na classificação de vinhos.

#### Variável alvo

A variável alvo definida foi a coluna **Quality**, pois ela informa a qualidade do vinho. Com base nas características físico-químicas, os modelos de machine learning podem prever a qualidade de novos vinhos.

#### Dataset

<table>
<tr><th>Campo</th><th>Valor</th></tr>
<tr><td>Fonte</td><td>https://www.kaggle.com/datasets/yasserh/wine-quality-dataset</td></tr>
<tr><td>Linhas × colunas</td><td>1143 x 13</td></tr>
<tr><td>Período / versão</td><td>1</td></tr>
</table>

Descrição das variáveis principais:

| Variável | Tipo | Descrição |
|-----------|------|------------|
| Acidez fixa (Fixed Acidity) | Número decimal | Quantidade de ácidos não voláteis presentes no vinho. |
| Acidez volátil (Volatile Acidity) | Número decimal | Representa os ácidos voláteis, principalmente o ácido acético. |
| Ácido cítrico (Citric Acid) | Número decimal | Contribui para o frescor e equilíbrio sensorial. |
| Açúcar residual (Residual Sugar) | Número decimal | Quantidade de açúcar que permanece após a fermentação. |
| Cloretos (Chlorides) | Número decimal | Indicador da concentração de sais no vinho. |
| Dióxido de enxofre livre | Número decimal | Proteção contra oxidação e microrganismos. |
| Dióxido de enxofre total | Número decimal | Conservante e estabilizante. |
| Densidade | Número decimal | Relacionada à composição do vinho. |
| pH | Número decimal | Mede a acidez química do vinho. |
| Sulfatos | Número decimal | Auxiliam na preservação e estrutura do vinho. |
| Teor alcoólico | Número decimal | Influencia corpo, aroma e percepção de qualidade. |
| Quality | Número inteiro | Variável-alvo prevista pelo modelo. |
| ID | Número inteiro | Identificador da base. |

### 4. Como reproduzir

```bash
git clone <URL_DO_REPOSITORIO>
cd <NOME_DO_REPOSITORIO>

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

pip install -r requirements.txt
jupyter notebook
```
Baixe o dataset e coloque o arquivo bruto em data/raw/ (os dados não são versionados — veja data/README.md).

Depois execute os notebooks nesta ordem:

<table>
<tr><th>#</th><th>Notebook</th><th>O que faz</th></tr>
<tr><td>1</td><td>notebooks/01_eda.ipynb</td><td>Análise exploratória</td></tr>
</table>

**Semente fixa:** RANDOM_STATE = 42

### 5. Resultados

| Modelo | Acurácia | Precisão | Recall | F1 | AUC-ROC |
|---------|----------|----------|--------|----|---------|
| Regressão Logística | 0.79 | 0.36 | 0.74 | 0.48 | 0.89 |
| Árvore de Decisão | 0.85 | 0.44 | 0.59 | 0.51 | 0.75 |
| Random Forest | 0.86 | 0.49 | 0.70 | 0.58 | 0.92 |

**Modelo escolhido:** Random Forest. O modelo apresentou o melhor desempenho geral entre os avaliados, alcançando os melhores resultados nas métricas analisadas.

### 6. Principais conclusões

1. **Álcool:** costuma estar ligado à maturação da uva e a uma fermentação completa, sendo um dos fatores mais influentes na qualidade.
2. **Acidez volátil:** principal fator negativo. O controle de higiene, oxigênio e temperatura ajuda a reduzir seu impacto.
3. **Sulfatos:** níveis adequados contribuem para preservação e qualidade do vinho.

#### Limitações e próximos passos

O ideal é acompanhar a maturação da uva e a fermentação para monitorar o teor alcoólico, controlar oxigênio, temperatura e higiene do processo para reduzir a acidez volátil e garantir níveis adequados de sulfatos para preservar a qualidade do vinho.

### 7. Estrutura do repositório
.
├── data/          dados brutos (raw) e tratados (processed) — não versionados
├── notebooks/     análise
└── docs/          apresentação executiva

### 8. Tecnologias

- Python 3.12
- Pandas
- NumPy
- Seaborn
- Scikit-learn
