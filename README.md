# Challenge Telecom X: Análise de Evasão de Clientes

## 📖 Descrição do Projeto

Este projeto foi desenvolvido como parte do programa Oracle Next Education - Alura, na trilha de Data Science. O objetivo principal é realizar uma análise exploratória de dados (EDA) sobre um conjunto de dados de uma empresa fictícia de telecomunicações, a Telecom X, para identificar os principais fatores que levam à evasão de clientes (churn). A partir dos insights gerados, busca-se fornecer recomendações que possam auxiliar a empresa a reduzir essa taxa.

---

## 🎯 Objetivo

* Realizar a extração, limpeza e transformação dos dados dos clientes.
* Conduzir uma análise exploratória detalhada para identificar padrões e correlações relacionadas ao churn.
* Visualizar as distribuições de dados e as relações entre variáveis.
* Sumarizar os principais achados e insights sobre os motivadores da evasão de clientes.
* Propor recomendações acionáveis para a Telecom X com base na análise realizada.

---

## 📂 Estrutura do Repositório

* **/challenge_telecom_x_churn.ipynb**: Notebook Jupyter principal contendo todo o processo de análise, desde a extração e limpeza dos dados, passando pela transformação, análise exploratória (EDA), até a elaboração do relatório final com conclusões e recomendações.
* **/README.md**: Este arquivo, fornecendo uma visão geral do projeto.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

* **Linguagem:** Python 3.x
* **Bibliotecas Principais:**
    * Pandas: Para manipulação e análise de dados tabulares.
    * NumPy: Para operações numéricas (utilizado para `np.nan`).
    * Matplotlib: Para a criação de gráficos estáticos e visualizações.
    * Seaborn: Para visualizações estatísticas mais elaboradas.
* **Ambiente:** Jupyter Notebook (utilizado via Google Colab).

---

##  methodological Metodologia Aplicada

O projeto seguiu as seguintes etapas principais do processo de análise de dados:

1.  **Extração de Dados:**
    * Carregamento do conjunto de dados `TelecomX_Data.json` a partir de uma URL (raw link do GitHub).
    * Normalização da estrutura JSON aninhada para um formato tabular utilizando `pandas.json_normalize()`.

2.  **Limpeza e Tratamento de Dados:**
    * Inspeção inicial da estrutura, tipos de dados e valores ausentes.
    * Tratamento de valores ausentes na coluna `account_Charges_Total` (imputação com 0.0 para clientes com `customer_tenure = 0` após conversão de strings problemáticas para numérico).
    * Tratamento de strings vazias na coluna `Churn` (conversão para `NaN` e subsequente remoção das linhas afetadas).
    * Verificação e confirmação da ausência de dados duplicados.
    * Correção do tipo de dado da coluna `account_Charges_Total` para numérico (`float64`).

3.  **Transformação de Dados e Engenharia de Features:**
    * Criação da coluna `Contas_Diarias` a partir de `account_Charges_Monthly`.
    * Mapeamento de colunas categóricas com respostas "Yes"/"No" para formato binário (1/0).
    * Mapeamento de colunas categóricas com três estados (ex: "Yes", "No", "No X service") para formato binário (1/0), onde "No X service" foi tratado como 0.
    * Padronização dos nomes das colunas (substituindo `.` por `_`).

4.  **Análise Exploratória de Dados (EDA):**
    * Análise descritiva geral do DataFrame (`df.describe(include='all')`).
    * Análise da distribuição da variável alvo `Churn` (contagens e proporções, visualizadas com gráficos de barras e pizza).
    * Análise da distribuição de outras variáveis categóricas chave (`value_counts()`, gráficos de barras).
    * Análise da distribuição de variáveis numéricas chave (histogramas, KDEs).
    * Análise bivariada para entender a relação entre cada variável preditora e a variável `Churn` (usando tabelas de contingência, taxas de churn por categoria, e visualizações como boxplots e histogramas/KDEs agrupados).

5.  **Elaboração do Relatório:**
    * Consolidação de todo o processo, análises, insights e recomendações diretamente no notebook.

---

## 🚀 Principais Insights e Conclusões (Resumo)

Exemplo:
* Clientes com contratos mensais (`Month-to-month`) demonstraram uma taxa de churn significativamente mais alta.
* O tempo de contrato (`customer_tenure`) tem uma correlação negativa com o churn: clientes mais novos são mais propensos a evadir.
* Cobranças mensais mais elevadas e o uso de "Electronic check" como método de pagamento também foram associados a um aumento na taxa de churn.
* *Para mais detalhes, consulte a seção "Conclusões e Insights" no notebook `challenge_telecom_x_churn.ipynb`.*

---

## ⚙️ Como Executar o Projeto

1.  Abra o notebook `challenge_telecom_x_churn.ipynb` em um ambiente que suporte Jupyter Notebooks e tenha as bibliotecas Python listadas acima instaladas (Google Colab é uma opção recomendada e já configurada para carregar os dados da URL).
2.  Execute as células sequencialmente de cima para baixo.
3.  O conjunto de dados é carregado automaticamente a partir de uma URL pública no início do notebook.

---

## 👤 Autor(a)

* **Vitor Maçal de Freitas**
* **LinkedIn:** https://www.linkedin.com/in/vitor-freitas1/
* **GitHub:** https://github.com/vitor-freitas1
