# Análise Descritiva de Acidentes nas Rodovias Federais (PRF 2026)

**Aluno:** Arthur Cavalari Appel  
**Disciplina:** Análise Exploratória de Dados / Estatística Descritiva  
**Fonte dos Dados:** [Dados Abertos da Polícia Rodoviária Federal (PRF)](https://www.gov.br/prf/pt-br/acesso-a-informacao/dados-abertos/dados-abertos-da-prf)

---

## 📌 Sobre o Projeto

Este projeto consiste em uma análise estatística descritiva e exploratória do banco de dados de acidentes de trânsito em rodovias federais brasileiras registrados pela PRF (dados de janeiro a julho de 2026).

O objetivo principal é compreender os fatores de risco que afetam a severidade e a letalidade dos acidentes, avaliando variáveis como fase do dia, condições meteorológicas, perfil dos dias da semana e a influência de acidentes graves (outliers) na distribuição dos dados.

---

## 🔍 Perguntas de Pesquisa & Principais Descobertas

### 1. **Fase do Dia e Fatalidade**
* **Pergunta:** O amanhecer ou o anoitecer são momentos mais letais do que o pleno dia ou a plena noite?
* **Achado:** O **Amanhecer** registrou a maior taxa de fatalidade (**11,80%** dos acidentes resultaram em óbitos), seguido pela **Plena Noite** (10,47%), **Anoitecer** (6,95%) e **Pleno Dia** (5,04%).
* **Interpretação:** A combinação de fadiga ao final de viagens noturnas, ofuscamento da visão pelo sol horizontal e menor fluxo de veículos (que induz maior velocidade) torna o amanhecer proporcionalmente mais severo.

### 2. **Condição Meteorológica e Risco Percebido**
* **Pergunta:** A chuva torna os acidentes mais letais que o céu claro, ou o nevoeiro/neblina é o real risco extremo?
* **Achado:** O **Nevoeiro/Neblina** é a condição de maior risco relativo, com **12,26%** de acidentes fatais. Curiosamente, acidentes sob **Chuva** apresentaram taxa de fatalidade de **6,55%**, menor do que em dias de **Céu Claro** (7,44%) e **Nublado** (7,64%).
* **Interpretação:** Fenômeno da *compensação de risco*: sob chuva, os motoristas reconhecem o perigo e tendem a reduzir a velocidade e aumentar a atenção. Em dias de céu claro, o excesso de confiança resulta em velocidades mais altas e acidentes mais gravosos.

### 3. **Impacto de Outliers (Mega-Acidentes)**
* **Pergunta:** Como os acidentes discrepantes (outliers pelo método do IQR) impactam os indicadores gerais?
* **Achado:** Acidentes com 5 ou mais pessoas representam **9,33%** da base (outliers). Nesses acidentes, a média de mortes salta de **0,06** (acidentes até 4 pessoas) para **0,318** — uma severidade **5,3 vezes maior**.
* **Interpretação:** Embora a mediana de envolvidos por acidente seja 2, a ocorrência de engavetamentos e acidentes com veículos coletivos (ônibus/vans) gera caudas longas à direita na distribuição, exigindo logística diferenciada de resgate.

### 4. **Fim de Semana vs. Dias Úteis**
* **Pergunta:** Acidentes no fim de semana envolvem mais pessoas ou são mais graves?
* **Achado:** Nos finais de semana, a média de envolvidos (**2,67**) e a taxa de mortes por acidente (**0,091**) são superiores às registradas em dias úteis (**2,61** envolvidos e **0,080** mortes).
* **Interpretação:** Alteração do perfil do tráfego: nos dias úteis predominam transporte de cargas e viagens individuais de trabalho; nos finais de semana aumentam os deslocamentos de lazer com veículos cheios (famílias/amigos) associados a cansaço e consumo de álcool.

---

## 📊 Síntese Estatística do Dataset

O dataset analisado contém **33.694 ocorrências** e **30 colunas**. Abaixo o resumo das variáveis quantitativas principais:

| Variável | Média | Mediana | Desvio Padrão | Mínimo | Máximo | Coef. Variação (%) |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Pessoas (`pessoas`)** | 2,64 | 2,0 | 2,019 | 1 | 88 | 76,46% |
| **Feridos (`feridos`)** | 1,15 | 1,0 | 1,209 | 0 | 48 | 105,09% |
| **Veículos (`veiculos`)** | 2,00 | 2,0 | 1,113 | 1 | 23 | 55,43% |
| **Mortos (`mortos`)** | 0,085 | 0,0 | 0,340 | 0 | 11 | 398,42% |

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** Python 3
- **Manipulação e Análise de Dados:** `pandas`, `numpy`
- **Visualização de Dados:** `matplotlib`, `seaborn`
- **Ambiente de Desenvolvimento:** Jupyter Notebook / Google Colab

---

## 📁 Estrutura do Repositório

```text
.
├── datatran2026.csv                   # Base de dados de acidentes da PRF (2026)
├── Trabalho_1_Analise_Descritiva.ipynb  # Notebook com código, gráficos e interpretações
└── README.md                          # Documentação do projeto
```

---

## 🚀 Como Executar o Projeto

1. **Clone o repositório:**
   ```bash
   git clone <URL_DO_SEU_REPOSITORIO>
   cd <NOME_DO_REPOSITORIO>
   ```

2. **Instale as dependências necessárias:**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

3. **Execute o Jupyter Notebook:**
   ```bash
   jupyter notebook Trabalho_1_Analise_Descritiva.ipynb
   ```
   *Alternativamente, você pode abrir e rodar o notebook diretamente no Google Colab ou VS Code.*

---

## 💡 Conclusão e Limitações

- **Associação vs. Causalidade:** Os achados mostram correlações comportamentais e contextuais, não relação de causalidade direta.
- **Limitação de Tráfego:** Os dados representam a gravidade relativa dos acidentes registrados, sem ponderação pelo volume total de veículos em circulação.
