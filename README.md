## MVP de Análise de Dados

### Contexto

Este projeto visa desenvolver um MVP (Minimum Viable Product) de análise de dados, abordando desde a definição do problema até a fase de pré-processamento. O projeto utiliza um conjunto de dados de campanhas de *marketing* de uma instituição bancária portuguesa, disponível em: https://archive.ics.uci.edu/dataset/222/bank+marketing.

O objetivo principal é **prever a probabilidade de um cliente adquirir um produto bancário** durante a campanha de *marketing* atual. Para isso, são utilizados dados pessoais do cliente, informações de crédito e histórico de interações com campanhas anteriores. 

### Descrição do Problema

O problema em questão é classificado como um **problema de aprendizado não supervisionado**, pois o conjunto de dados não fornece informações sobre quais clientes realmente adquiriram o produto, ou seja, não temos uma variável alvo definida. 

As **premissas** para o desenvolvimento do projeto incluem:

*   A utilização de um conjunto de dados real, referente a campanhas de *marketing* de um banco português.
*   Considerar que o objetivo é prever a probabilidade de aquisição de um produto, apesar da falta de rótulos no conjunto de dados.
*   Utilizar a linguagem Python e bibliotecas como Pandas, Matplotlib, Seaborn e Missingno para análise e tratamento dos dados.

### Atributos do Dataset

O conjunto de dados é composto por **16 atributos** que descrevem o perfil dos clientes e seu histórico de interação com o banco. Esses atributos podem ser divididos em quatro categorias:

**Dados pessoais do cliente:**

*   **age:** Idade do cliente.
*   **job:** Ocupação do cliente.
*   **marital:** Estado civil.
*   **education:** Nível de escolaridade.
*   **default:** Indica se o cliente possui crédito em inadimplência.
*   **balance:** Saldo médio anual em euros.
*   **housing:** Indica se o cliente possui financiamento imobiliário.
*   **loan:** Indica se o cliente possui empréstimo pessoal.

**Dados do último contato da campanha atual:**

*   **contact:** Tipo de comunicação utilizada no último contato.
*   **day:** Dia do mês do último contato.
*   **month:** Mês do último contato.
*   **duration:** Duração do último contato em segundos.

**Dados de campanhas anteriores:**

*   **campaign:** Número de contatos realizados durante a campanha atual.
*   **pdays:** Número de dias desde o último contato em uma campanha anterior (-1 significa que o cliente não foi contatado anteriormente).
*   **previous:** Número de contatos realizados antes da campanha atual.
*   **poutcome:** Resultado da campanha de marketing anterior.

### Análise de Dados

A análise de dados foi conduzida utilizando **estatísticas descritivas e visualizações**, com o objetivo de:

*   **Compreender a distribuição dos dados:** histogramas e gráficos de densidade foram utilizados para visualizar a distribuição das variáveis quantitativas, como idade, saldo e duração das chamadas. 
*   **Identificar outliers:** boxplots foram utilizados para visualizar a dispersão dos dados e identificar outliers em atributos como saldo e duração das chamadas.
*   **Analisar a relação entre variáveis:** scatterplots foram utilizados para identificar possíveis relações entre variáveis quantitativas, como duração da chamada e saldo.
*   **Comparar grupos:** histogramas e gráficos de pizza foram utilizados para comparar a distribuição de variáveis em diferentes grupos, como clientes que adquiriram ou não o produto em campanhas anteriores.

### Pré-processamento de Dados

O pré-processamento de dados teve como objetivo **preparar os dados para a etapa de modelagem**, realizando operações como:

*   **Tratamento de missings:** valores faltantes foram tratados de diferentes maneiras, como substituição por zero (para as colunas 'previous' e 'balance') e remoção de linhas com informações faltantes em atributos cruciais, como 'job', 'education', 'contact' e 'poutcome'.
*   **Discretização:** variáveis contínuas, como saldo e duração da chamada, foram transformadas em categorias ordinais, criando os atributos 'Saldo_discretizado' e 'Duracao_discretizada'.
*   **One-hot encoding:** variáveis categóricas nominais, como estado civil e nível de escolaridade, foram transformadas em colunas binárias utilizando a técnica one-hot encoding.

### Conclusões Preliminares

A análise exploratória dos dados permitiu extrair algumas conclusões preliminares sobre o conjunto de dados, como:

*   A maioria dos clientes do banco são casados, possuem nível secundário de escolaridade e atuam nas áreas de colarinho azul, gestão e técnico.
*   A maioria dos contatos da campanha atual foram realizados via celular, e o mês de maio apresentou o maior número de ligações.
*   Há uma diferença significativa na porcentagem de clientes com financiamento imobiliário entre aqueles que adquiriram e recusaram produtos em campanhas anteriores.

