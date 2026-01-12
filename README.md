# Análise da Desigualdade Educacional no ENEM - Belo Horizonte

Este projeto apresenta uma investigação técnica sobre as disparidades de desempenho entre alunos de escolas públicas e privadas em Belo Horizonte, utilizando os microdados do ENEM 2024. A análise percorre desde a extração e tratamento dos dados até a geração de métricas de elite e distribuição estatística.

## Objetivos
* Comparar o desempenho acadêmico em cinco áreas: Ciências da Natureza, Ciências Humanas, Linguagens, Matemática e Redação.
* Quantificar a desigualdade socioeducacional através da distribuição de alunos em decis de nota.
* Identificar a probabilidade de sucesso (Razão de Elite) conforme a rede de ensino em Belo Horizonte.

## Arquitetura de Dados
O pipeline foi estruturado seguindo a arquitetura de medalhões para garantir a linhagem e integridade da informação:
* **Camada Bronze:** Dados brutos dos microdados nacionais filtrados geograficamente para o município de Belo Horizonte.
* **Camada Prata:** Limpeza, padronização de tipos e mapeamento de categorias administrativas como Federal, Estadual, Municipal e Privada.
* **Camada Ouro:** Modelagem analítica final com binarização de redes (Pública vs. Privada) e cálculo de decis de desempenho padronizados.

## Engenharia e Performance
Para otimizar o fluxo de dados e o armazenamento, utilizou-se o formato Apache Parquet com compressão Gzip.
* **Armazenamento Colunar:** Melhora a performance em consultas de grandes volumes e agregações.
* **Preservação de Tipos:** Garante que as categorias administrativas e os decis (D01 a D10) sejam mantidos sem perda de esquema entre as sessões.
* **Eficiência de Compressão:** Redução significativa do espaço em disco para armazenamento em ambientes de nuvem como Google Drive.

## Análises e Insights
* **Distribuição por Decis:** A utilização de gráficos de barras empilhadas de 100% permite visualizar a predominância acentuada da rede privada nos decis de maior pontuação (D09 e D10).
* **Gargalos por Matéria:** A análise de funil evidencia como o fluxo de alunos para os níveis de excelência varia drasticamente entre as redes pública e privada, especialmente em matérias como Matemática.
* **Métrica de Elite:** Cálculo da razão de chance de um aluno atingir o decil superior, fornecendo um KPI direto da disparidade educacional regional.

## Tecnologias Utilizadas
* **Python 3.12:** Linguagem base para o desenvolvimento do projeto.
* **Pandas e NumPy:** Bibliotecas utilizadas para transformação, limpeza e agregação de dados.
* **Plotly:** Ferramenta para geração de painéis interativos e subplots analíticos.
* **PyArrow:** Motor de processamento utilizado para a manipulação eficiente de arquivos Parquet.

## Estrutura do Repositório
* **projeto_enem_bh.ipynb:** Notebook principal contendo todo o pipeline de processamento e análise.
* **README.md:** Documentação técnica detalhada do projeto.

---
*Este projeto demonstra competências em Engenharia de Dados, Análise Exploratória (EDA) e Visualização de Dados aplicadas a problemas sociais complexos.*
