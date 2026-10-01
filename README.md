# clorado
Projeto sobre o artigo de Jessica (UFPE - LSA)
# Simulador DBPs – Subprodutos da Desinfecção em Efluente Clorado

🔗 **Acesse:** [https://aluisiopereirati.github.io/clorado/](https://aluisiopereirati.github.io/clorado/)

## Sobre o projeto

O **Simulador DBPs** é uma aplicação web interativa desenvolvida no contexto de pesquisas da Universidade Federal de Pernambuco (UFPE), na área de Engenharia Civil e Ambiental, com foco na análise, caracterização, especiação e modelagem de subprodutos da desinfecção (*Disinfection By-Products – DBPs*) em efluentes submetidos à cloração.

A ferramenta integra procedimentos de curadoria de dados laboratoriais, análise de concentrações de compostos halogenados, avaliação de padrões de incorporação de bromo, comparação com limites de referência e aplicação de modelos de aprendizado de máquina e redes neurais artificiais.

O simulador foi estruturado a partir dos dados experimentais da Estação de Tratamento de Esgoto (ETE) Mangueira, em Recife – PE, considerando amostras de efluentes clorados com hipoclorito de sódio produzido por eletrólise de salmoura.

O conjunto de dados contempla **20 subprodutos da desinfecção, 51 réplicas e 17 campanhas experimentais**, realizadas entre maio e agosto de 2025.

## Objetivos

* Organizar e qualificar os dados laboratoriais de DBPs.
* Avaliar a ocorrência e a frequência de detecção dos diferentes compostos.
* Corrigir inconsistências no cálculo das concentrações analíticas.
* Investigar os padrões de especiação e incorporação de halogênios.
* Comparar as concentrações obtidas com valores de referência regulatórios.
* Aplicar técnicas de aprendizado de máquina para estimar concentrações de determinados DBPs.
* Investigar relações estatísticas, agrupamentos e padrões multivariados entre os compostos.
* Disponibilizar uma interface interativa para exploração e interpretação dos resultados científicos.

## Funcionalidades

A aplicação está organizada em cinco módulos principais:

### 1. Visão geral

Apresenta uma síntese dos resultados experimentais, incluindo:

* Indicadores gerais do conjunto de dados.
* Frequência de detecção por analito.
* Distribuição dos compostos por classes químicas.
* Principais padrões identificados nas campanhas.
* Síntese dos resultados da modelagem preditiva.

### 2. Curadoria e qualidade dos dados

Módulo destinado à avaliação e ao tratamento dos dados analíticos.

Principais recursos:

* Calculadora de concentração a partir da área cromatográfica.
* Aplicação das curvas de calibração.
* Identificação de concentrações espúrias decorrentes de células vazias.
* Avaliação dos padrões internos (*Internal Standards*).
* Análise da recuperação relativa dos padrões.
* Registro das correções aplicadas aos dados.
* Consulta aos parâmetros analíticos e tempos de retenção dos compostos.

### 3. Especiação e limites de referência

Permite explorar a distribuição dos compostos halogenados e calcular indicadores relacionados à composição química dos DBPs.

Funcionalidades:

* Soma dos trialometanos (TTHM).
* Soma dos ácidos haloacéticos (HAA5 e HAA9).
* Análise de compostos nitrogenados e cetonas halogenadas.
* Cálculo dos fatores de incorporação de bromo (BIF e BSF).
* Simulação de concentrações por amostra.
* Comparação com valores de referência brasileiros e internacionais.

### 4. Inteligência artificial e redes neurais

Integra modelos de aprendizado de máquina para simulação e estimativa de concentrações de subprodutos da desinfecção.

O módulo contempla três tarefas preditivas:

| Tarefa | Variável de saída | Variáveis de entrada                    |
| ------ | ----------------- | --------------------------------------- |
| A      | HAA9              | BDCM, DBCM, TBM, DCAN, DBAN e 1,1,1-TCP |
| B      | TTHM              | MCAA, MBAA, DCAA, TCAA, DBCAA e TBAA    |
| C      | DCAN              | BDCM, DBCM e TBM                        |

Modelos contemplados:

* Redes Neurais Artificiais (RNA / MLP).
* Regressão Linear Múltipla (MLR).
* Ridge Regression.
* Partial Least Squares (PLS).
* Support Vector Regression (SVR).
* K-Nearest Neighbors (kNN).
* Random Forest.
* Gradient Boosting.

Indicadores e recursos de avaliação:

* R² de validação cruzada.
* RMSE e MAE.
* KGE e PBIAS.
* Importância das variáveis por permutação.
* Gráficos de valores observados versus previstos.
* Simulação interativa das entradas e respostas dos modelos.

As redes neurais foram treinadas em Python com Scikit-learn e seus parâmetros foram incorporados à aplicação para execução das previsões em JavaScript.

### 5. Estrutura e análise multivariada dos dados

Módulo dedicado à investigação das relações estatísticas e dos padrões de distribuição dos compostos.

Inclui:

* Matriz de correlação de Spearman.
* Visualização de mapas de calor (*heatmaps*).
* Análise de Componentes Principais (PCA).
* Agrupamento por K-means.
* Séries temporais das concentrações por campanha.
* Comparação das médias e desvios-padrão dos principais indicadores.

## Tecnologias utilizadas

| Tecnologia        | Aplicação                                      |
| ----------------- | ---------------------------------------------- |
| HTML5             | Estrutura da aplicação web                     |
| CSS3              | Interface, responsividade e identidade visual  |
| JavaScript        | Processamento, cálculos e interatividade       |
| Python            | Preparação dos dados e treinamento dos modelos |
| Scikit-learn      | Modelagem estatística e aprendizado de máquina |
| Redes Neurais MLP | Modelagem preditiva                            |
| SVG               | Construção de gráficos e visualizações         |

A aplicação é disponibilizada em um único arquivo HTML, com estilos, scripts, dados e parâmetros dos modelos incorporados.

## Estrutura do projeto

```text
simulador-DBPs/
│
├── README.md
│
├── index.html
│
└── docs/
    └── imagens/
```

O arquivo `index.html` corresponde à aplicação web principal.

## Como executar

Não é necessário instalar Python, bibliotecas ou configurar um servidor para utilizar a versão HTML disponibilizada.

**Execução local:**

1. Clone o repositório:

```bash
git clone https://github.com/aluisiopereirati/clorado.git
```

2. Acesse a pasta:

```bash
cd simulador-DBPs
```

3. Abra o arquivo `index.html` diretamente no navegador.

Também é possível disponibilizar a aplicação pela funcionalidade **GitHub Pages**, permitindo seu acesso pela internet.

## Resultados científicos e aplicações

A ferramenta possibilita explorar os resultados experimentais e investigar relações entre diferentes classes de subprodutos da desinfecção.

Entre os resultados apresentados na aplicação estão:

* Identificação de padrões de ocorrência de compostos bromados.
* Avaliação das relações entre trialometanos, haloacetonitrilas e ácidos haloacéticos.
* Investigação da capacidade preditiva dos modelos de aprendizado de máquina.
* Identificação de limitações na estimativa de determinadas classes de DBPs.
* Análise da variabilidade das concentrações entre campanhas experimentais.

A aplicação também evidencia a importância da curadoria e da qualidade dos dados laboratoriais antes da construção de modelos preditivos.

## Limitações e considerações

Os resultados apresentados são específicos do conjunto experimental utilizado no desenvolvimento do simulador.

As previsões dos modelos devem ser interpretadas considerando o tamanho amostral, as faixas observadas no treinamento e as limitações da validação cruzada.

Os valores de referência regulatórios apresentados na aplicação são utilizados para comparação de magnitude e não representam, por si só, uma avaliação de conformidade de efluentes destinados ao lançamento ou ao reúso.

Os parâmetros físico-químicos e a dose de cloro não estavam disponíveis na planilha experimental utilizada na aplicação. Portanto, a previsão baseada nessas variáveis depende da disponibilização dos dados complementares.

## Contexto institucional e científico

**Instituição:** Universidade Federal de Pernambuco (UFPE)
**Área:** Engenharia Civil e Ambiental
**Unidade experimental:** Estação de Tratamento de Esgoto (ETE) Mangueira
**Localização:** Recife – Pernambuco, Brasil
**Período experimental:** Maio a agosto de 2025

**Autores associados ao projeto:**

Rocha, Pereira, Magnus e Florêncio.

## Contribuições

Contribuições científicas e técnicas são bem-vindas, especialmente nas áreas de:

* Engenharia sanitária e ambiental.
* Química analítica e ambiental.
* Tratamento de efluentes.
* Ciência de dados.
* Inteligência artificial.
* Modelagem estatística e preditiva.
* Monitoramento da qualidade da água.

## Licença e utilização

A licença de distribuição e reutilização do código e dos dados deverá ser definida pelos autores e responsáveis pelo projeto antes da publicação pública do repositório.

A utilização dos dados experimentais e dos parâmetros dos modelos deve respeitar as condições de autorização, autoria e integridade científica da pesquisa original.

---

**Simulador DBPs – UFPE**
*Ciência de dados, inteligência artificial e modelagem aplicada à engenharia ambiental.*

