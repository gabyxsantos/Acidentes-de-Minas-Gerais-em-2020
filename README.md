# Análise de Acidentes Rodoviários em Minas Gerais (2020)

## 📝 Descrição do Projeto

Este repositório contém uma análise de dados completa sobre os acidentes ocorridos nas rodovias federais de Minas Gerais em 2020. O projeto foi desenvolvido como um estudo de caso para o processo seletivo da EstatMG, a empresa júnior de Estatística da Universidade Federal de Minas Gerais.

O objetivo foi simular um desafio de consultoria real, abordando um problema complexo e transformando dados brutos em insights estratégicos. A análise demonstra habilidades em limpeza de dados, visualização (incluindo geoespacial e interativa), aplicação de testes estatísticos (Qui-Quadrado, Kruskal-Wallis) e interpretação de resultados para gerar recomendações acionáveis.

## 🎯 Objetivo do Cliente

A análise foi guiada pela seguinte solicitação:
> "Meu objetivo é avaliar as principais causas de acidentes nas rodovias de Minas Gerais, bem como um mapeamento dos tipos de acidentes e das rodovias. Também gostaria de entender os acidentes de acordo com variáveis relativas a tempo: dia da semana e mês. As demais associações ficam a critério de vocês e podem utilizar as análises que julgarem necessárias."

## 💾 Fonte dos Dados

O conjunto de dados utilizado foi o arquivo `Acidentes_2020.xlsx`, contendo registros detalhados de cada ocorrência, incluindo informações como data, localização (BR, KM, latitude, longitude), tipo de acidente, condições da via, condições meteorológicas e número de vítimas.

## 🛠️ Ferramentas e Bibliotecas Utilizadas

* **Linguagem:** Python 3
* **Bibliotecas Principais:**
    * **Pandas:** Para manipulação e limpeza dos dados.
    * **Matplotlib & Seaborn:** Para a criação de gráficos estáticos e visualizações de dados.
    * **Folium:** Para a criação de mapas interativos e geolocalização dos acidentes.
    * **SciPy:** Para a execução de testes estatísticos (Qui-Quadrado e Kruskal-Wallis).
    * **NumPy:** Para a criação da variável de gravidade de forma otimizada.
    * **IPython.display:** Para formatação de texto no notebook.

## 🚀 Principais Análises e Insights

A análise foi estruturada para contar uma história, partindo de uma visão macro para investigações específicas e aprofundadas.

### 1. Análise Geográfica: Onde os Acidentes se Concentram?
* Um **mapa interativo com clusters** revelou uma alta concentração de acidentes na Região Metropolitana de Belo Horizonte e nos principais eixos rodoviários que cortam o estado.
* As rodovias **BR-381** e **BR-040** foram identificadas como as que possuem o maior volume absoluto de acidentes, tanto no geral quanto em categorias de alta gravidade (com feridos graves ou mortos).

### 2. Análise Temporal: Quando os Riscos Aumentam?
* A distribuição mensal de acidentes em 2020 foi **fortemente impactada pela pandemia de COVID-19**, com uma queda brusca durante o lockdown inicial (Março-Maio) e picos no segundo semestre, associados à flexibilização das restrições e feriados.
* Foi identificado um **aumento significativo no volume de acidentes nos fins de semana** (Sexta, Sábado e Domingo). A relevância dessa diferença foi validada estatisticamente através do **Teste de Kruskal-Wallis (p < 0.05)**.

### 3. Fatores de Risco e Associações: Por que os Acidentes Ocorrem?
* **Condição Meteorológica vs. Tipo de Acidente:** Através do **Teste Qui-Quadrado (p ≈ 0)**, foi comprovado que existe uma associação estatisticamente significativa entre o tempo e o tipo de acidente. Um heatmap normalizado mostrou que, embora a maioria dos acidentes ocorra com céu claro, a **proporção** de acidentes como "Saída de Pista" aumenta drasticamente sob chuva.
* **Tipo de Pista vs. Gravidade:** Foi criada uma variável categórica de `gravidade` (Fatal, Grave, Leve). O **Teste Qui-Quadrado (p ≈ 0)** confirmou que o tipo de pista está associado à gravidade. Gráficos de barras proporcionais mostraram que "Pista Simples" concentra uma porcentagem maior de acidentes fatais e graves em comparação com pistas duplicadas.

### 4. Estudos de Caso: Investigando os Hotspots
* **BR-381 (KM 490):** Identificado como um hotspot de **congestionamento**. A alta frequência de "Colisões Traseiras" em um trecho de pista dupla na área urbana de Betim sugere que a causa principal é o alto fluxo e o efeito "anda-e-para", e não a geometria da via.
* **BR-040 (KM 511):** Identificado como um **gargalo de tráfego complexo** devido à sua proximidade com a CEASA-MG. A combinação de "Colisões Traseiras", "Tombamentos" e "Colisões Laterais" aponta para a perigosa interação entre veículos leves e o intenso tráfego de caminhões em manobras de entrada e saída.

## 📂 Estrutura do Repositório
```
.
├── Acidentes_2020.xlsx     # O arquivo de dados brutos utilizado na análise.
├── EstatMg.ipynb           # O Jupyter Notebook contendo todo o código, análises e conclusões.
├── README.md               # Este arquivo, explicando o projeto.
└── (Opcional) mapa_acidentes_mg_2020.html # O arquivo do mapa interativo gerado pelo Folium.
```

## 💻 Como Executar o Projeto

1.  **Clone este repositório:**
    ```bash
    git clone [URL_DO_SEU_REPOSITORIO]
    ```
2.  **Navegue até a pasta do projeto:**
    ```bash
    cd [NOME_DA_PASTA]
    ```
3.  **Instale as dependências:**
    ```bash
    pip install pandas openpyxl numpy matplotlib seaborn folium scipy
    ```
4.  **Execute o Notebook:**
    Abra o arquivo `EstatMg.ipynb` em um ambiente como Jupyter Notebook, JupyterLab ou Google Colab e execute as células na ordem. Certifique-se de que o arquivo `Acidentes_2020.xlsx` está na mesma pasta.
