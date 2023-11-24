### Sobre o problema

Considerado um dos maiores e melhores sistemas de saúde públicos do mundo, o SUS
beneficia cerca de 180 milhões de brasileiros e realiza por ano cerca de 2,8 
bilhões de atendimentos, desde procedimentos ambulatoriais simples a 
atendimentos de alta complexidade, como transplantes de órgãos. Os desafios, no
entanto, são muitos, cabendo ao Governo e à sociedade civil a atenção para 
estratégias de solução de problemas diversos, identificados, por exemplo, na 
gestão do sistema e também no subfinancimento da saúde (falta de recursos).

Paralelamente à realização de consultas, exames e internações, o SUS também 
promove campanhas de vacinação e ações de prevenção de vigilância sanitária, 
como fiscalização de alimentos e registro de medicamentos.

Algumas dessas camapanhas são focadas em doenças respiratórias, como a
campanha de vacinação contra a gripe, que ocorre anualmente, e mais recentemente
a campanha de vacinação contra a COVID-19. Ambas as doenças são classificadas
como SRAG (Síndrome Respiratória Aguda Grave), síndromes essas que só em 2023
foram responsáveis por mais de 200 mil atendimentos no SUS.

### Objetivo

A primeira tarefa é analisar os dados para apresentar quaisquer
insights.

Já a segunda consiste em criar e avaliar um classificador que seja capaz de
distinguir entre três tipos de doenças respiratórias: COVID-19, gripe e outras.

Por último, é necessário que os achados sejam resumidos em slides para avaliação.

### Sobre os dados

Os dados incluem:

- INFLUD23-16-10-2023: dados sobre os atendimentos de SRAG, como data de
atendimento, data de nascimento, sexo, etc.

### Métricas de avaliação

Para o modelo em questão, a **Log Loss** será métrica de avaliação principal,
pois é uma métrica que penaliza erros de classificação mais graves, e 
como o objetivo é identificar doenças respiratórias graves, como a COVID-19
e a gripe, é importante que o modelo não cometa tais erros, pois, nesse caso
o paciente pode não receber o tratamento adequado.

Entretanto, caso o modelo não apresente uma Log Loss significante, outras
métricas como o **F1 Score** e o **Recall** serão incluídas na avaliação para
uma análise mais robusta de desempenho.

### Melhorias

[⌛] Reduzir a Log Loss do modelo.

### Instruções para execução do projeto

Siga os seguintes passos para rodar o projeto localmente:

1. Clone o repositório:
```sh
git clone https://github.com/dnsrsdata/Respiratory_Analysis
```
2. Crie um ambiente virtual:
```sh
python -m venv venv
```
3. Ative o ambiente virtual de acordo com o seu sistema operacional.

4. Instale as dependências:
```sh
pip install -r requirements.txt
```

### Descrição dos arquivos

    - data
    |- raw
    | |- Dicionario_de_Dados.pdf  # Arquivo contendo a descrição dos dados
    | |- INFLUD23-16-10-2023.csv  # Dados sobre os atendimentos de SRAG
    |
    - images
    |- reports
    | |- INFLUD23-16-10-2023.html   # Relatório gerado pelo pandas profiling
    |- acertos_influenza.png  # Gráfico de waffle mostrando a taxa de acerto/erro do modelo para a classe influenza
    |- acertos_nao_covid_influenza.png  # Gráfico de waffle mostrando a taxa de acerto/erro do modelo para as classes que não são COVID-19 e influenza
    |- banner.png  # Banner utilizado no notebook da EDA
    |- funnel_internados_obitos_ppt.png  # Gráfico de funil sobre internações usado no ppt
    |- funnel_internados_obitos.png  # Gráfico de funil sobre internações usado no notebook da EDA
    |- maiores_agentes_causadores_obito_ppt.png  # Gráfico de barras sobre os maiores agentes causadores de óbito usado no ppt
    |- maiores_agentes_causadores_obito.png  # Gráfico de barras sobre os maiores agentes causadores de óbito usado no notebook da EDA
    |- media_idade_obitos.png  # Indicador mostrando a média de idade dos pacientes que foram à óbito
    |- numero_de_casos.png  # Indicador mostrando o número de casos de SRAG
    |- previsao_recall_e_acertos_covid_ppt.png  # Gráfico de waffle mostrando a taxa de acerto/erro do modelo para a classe Covid e o acerto em geral
    |- principais_agentes_ppt.png  # Gráfico de barras sobre os principais agentes causadores de SRAG usado no ppt    
    |- principais_agentes.png  # Gráfico de barras sobre os principais agentes causadores de SRAG usado no notebook da EDA
    |
    - notebooks
    |- EDA_Obitos_SRAGs.ipynb  # Notebook contendo a análise exploratória dos dados
    |- model_experimentation.ipynb  # Notebook contendo os experimentos com os modelos
    |
    - relatorio
    |- SRAGS.pdf  # Relatório em ppt usado para apresentar os achados 
    |
    - README.md  # Arquivo contando informações do projeto
    - requirements.txt # Arquivo contendo as dependências do projeto

### Resultados

Apesar do modelo ter obtidos resultados que seriam considerados ótimos em outros
tipos de problema, eu não recomendaria a sua utilização em um ambiente de
produção, pois como estamos lidando com doenças respiratórias graves, como a
COVID-19 e a gripe, é importante que o modelo não cometa muitos erros, pois
um diagnóstico errôneo pode levar a um tratamento inadequado. Além disso, certas
doenças são altamente contagiosas, e um diagnóstico errado pode levar a uma
maior disseminação da doença.
